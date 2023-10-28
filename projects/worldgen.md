---
layout: project
type: project
image: img/worldgen/preview-crop.png
title: "Procedurally Generated World"
date: 1
published: true
labels:
  - C++
  - OpenGL
  - Perlin Noise
summary: "Cool project to learn C++, memmory managnment, multithreading, OpenGL."
---

<video width="80%" controls>
  <source src="../img/worldgen/preview.mp4" type="video/mp4">
</video>

<h3>Introduction</h3>
The project was written to pass a C++ course, in addition, I wanted to do an interesting.

<h2>Memory management</h2>

In order to have the greatest control over memory, the whole world, the whole mesh is created manually, by the program. First, a rectangular chunk of size n:n:x is created, inside of which, based on the results of Perlin Noise, our triangular mesh is created, only on the surface side. Then only chunks within the field of view that is defined are displayed, and all chunks are stored in a unordered_map, so we are only limited by the maximum capacity of the unordered_map.

<h2>"Infinite" world</h2>
I use perlin noise to generate my map. In a nutshell, perlin noise is created by linear interpolation dot product of random gradient vectors.

<img class="img-fluid" src="../img/worldgen/PerlinExample.png">

Already knowing more or less what perlin noise is, it is smooth, its values pass smoothly and are in the range, for example, from 0 to 1, we can define its parameters so as to get the map we are interested in. We can enter the seedy, change the offset, change the number of octaves, frequency, amplitude. All this translates into our final result which is a finished world.
<a href="https://libnoise.sourceforge.net/glossary/index.html#perlinnoise">More about Perlin Noise</a>

<h2>Loading texture</h2>

Block textures are taken from a single file named "atlas" you need to pass the texture coordinates for the block then the program will load the appropriate textures and in OpenGL apply them to our block. It is also worth mentioning that blocks have walls only on the sides that are visible, so the textures are also applied only on that side, you can't see them from inside the block and other sides. Such a solution translates into the speed of world generation

<h2>Multithreading</h2>

Thanks to the nice multithreading in C++, I was able to use a separate thread to fill in the contents of chunks, so that each time a new chunk is drawn, the game doesn't stutter but loads the chunk at runtime on a separate thread.

<hr>

<a href="https://github.com/MyKarcio123/Studies-CPP-course"><i class="large github icon "></i>Source</a>
