---
layout: project
type: project
image: img/openGL/preview-second-crop.png
title: "Darwinian simulation with OpenGL"
date: 3
published: true
labels:
  - Java
  - OpenGL
summary: "Darwinian animal survival simulator, written for a college exercise, my first time with OpenGL."
---

<img class="img-fluid" src="../img/openGL/banner.png">
<h3>Introduction</h3>
This simulation was written as part of a college course called "Object Oriented Programming." The functionalities of the alpha version of my simulation. 
<ul>
<li> Animals are generated at random on the board, which are loaded from .obj files (this allowed me to learn the basics of 3D Graphics), </li> 
<li> One mouse click is one tick in the game. </li>
<li> Every tick, one animal can turn or move (this depends on the genotype that is input into the simulation), </li>
<li> When an animal enters a randomly generated plot of grass, the grass is eaten and a new one randomly appears, </li>
<li> The map is theoretically infinite (as long as there is enough memory), it expands as the animals move. </li>
</ul>
More interesting mechanics that I implemented:
<ul>
<li> Loading 3D models from a .obj file, </li>
<li> Animation system, </li>
<li> Map generation. </li>
</ul>
<h3>Loading three-dimensional models</h3>
In order for us to load three-dimensional models, we should know how they are made in the first place. Models in .obj format are nothing more than a collection of triangles in space. In the .obj file itself, we are interested in 4 blocks of information. The first block is the coordinate triples (X,Y,Z) responsible for the vertices of our triangles, denoted by the letter 'v'. The second block denoted by 'vt' are pairs of coordinates (X,Y), often referred to as uvs. These are coordinates with respect to the plane with texture graphics, so that the program knows how to fit textures to the triangle. The third block denoted by 'vn' are normal vectors, which are used for shadows, for example. We know from algebra that it is perpendicular to the plane, this block is not important for us because we are not using shadows for now. The last block is referred to by the letter f. In each line are given the indices of the vertices that form two triangles in space. 

<img class="img-fluid" src="../img/openGL/obj_explaned.avif">

<a href="https://all3dp.com/1/obj-file-format-3d-printing-cad/">A more detailed explanation on the obj format</a>

Once we know what an obj extension is, just importing models into our program is not all that difficult.

In order to generate our graphics on the screen we will need 3 arrays, which we will later pass to load them into VAO. These are an array of the coordinates of our vertices, an array of our uvs, and an array of the indices of our vertices that make up the triangle.

<a href="https://github.com/MyKarcio123/OOPlab/blob/main/Lab7/src/main/java/agh/ics/oop/renderEngine/ObjectLoader.java">Link</a>

<h3>Animation system</h3>

The animation system is simpler than it looks. An animation is nothing more than a small movement repeated every frame of the program. If we know in what position our object is and what position we are aiming at, we can easily calculate the vector in the direction of which our object is moving and every program frame add a small part of our vector, until our object is in the final position +/- a small value (this is because we may 'miss' our final vector).

<img src="../img/openGL/animation.gif" width="80%">


<a href="https://github.com/MyKarcio123/OOPlab/blob/main/Lab7/src/main/java/agh/ics/oop/renderEngine/AnimationController.java">Link</a>


<h3>Map generation.</h3>

Generating a map is not difficult either. The map is simply a cuboid (without some walls to make the program use less resources). I check if our map should be generated and if so, I adjust the uvs to whether it should be dirt or should be grass. Then if the animal enters the grass then the map is generated once again so that I change the appropriate uvs to display dirt instead of grass.

<img src="../img/openGL/bottom.png">

<a href="https://github.com/MyKarcio123/OOPlab/blob/main/Lab7/src/main/java/agh/ics/oop/renderEngine/Terrain.java">Link</a>
<hr>

<a href="https://github.com/MyKarcio123/OOPlab/tree/main/Lab7"><i class="large github icon "></i>Source code</a>
