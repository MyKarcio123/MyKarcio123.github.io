---
layout: project
type: project
image: img/darwin/preview-crop.png
title: "Darwinian simulation"
date: 4
published: true
labels:
  - Java
  - JavaFX
  - Scene Builder
  - Guava
summary: "Dawrin animal survival simulator written in a team of 3 as part of a college exercise"
---

<img class="img-fluid" src="../img/darwin/banner.png">
<h3>A short video showing how the project works</h3>
<video width="80%" controls>
  <source src="../img/darwin/simVid.mp4" type="video/mp4">
</video>
<h3>Introduction</h3>
This simulation was written as part of a credit project from a college course called "Object Oriented Programming." It was done in a team of 3 people. Simulation assumptions:
<ul>
<li>At the start, the user sees a UI that allows him to customize selected parameters (number of animals, type of map, number of plants)</li>
<li>Settings can be saved and loaded from a file</li>
<li>Animals are randomly generated on the board with a preset initial health (marked with a bar)</li>
<li>The animal has a random genotype, which determines how the animal moves</li>
<li>When two animals enter one field and have the appropriate health reproduction occurs, and the genotype of the child is a random combination of the genotypes of the parents (dependent on their health)</li>
<li>At any time during the simulation, we can view statistics</li>
<li>After stepping on an animal, we can track it (see its genotype)</li>
<li>To check how beautifully our map was generated we can use the minimap</li>
</ul>
You can choose different variations of our simulation.
The most interesting one is biomes, the map is procedurally divided into appropriate biomes (desert, swamp, jungle, forest, ice and snow), depending on the biome the simulation rules change.
<ul>
<li>Desert - instead of plants grow cacti, which take away the health of our animals</li>
<li>Swamp - the animal gets stuck in the mud, it takes two turns to move</li>
<li>Jungle - more and better plants grow, when eaten the animal gets more health</li>
<li>Forest - standard rules</li>
<li>Ice - the animal slides, walking two bars, no plants</li>
<li>Snow - stumps grow instead of plants, which give less health, in addition, it snows so every turn health is taken away</li>
</ul>
<h3>My tasks that I dealt with within the project</h3>
<ul>
<li>Main menu with the possibility of saving the selected configuration and loading it from a file <a href="https://github.com/MyKarcio123/OOPlab/blob/main/proj1/src/main/java/agh/ics/oop/gui/MainMenuController.java">Link</a></li>
<img class="img-fluid" src="../img/darwin/menu.png">
<li>All functionalities associated with the animal class (e.g., ability to eat, reproduce, die, give birth, draw genotype) <a href="https://github.com/MyKarcio123/OOPlab/blob/main/proj1/src/main/java/agh/ics/oop/Animal.java">Link</a></li>
<li>A variant of the simulation in which biomes are procedurally created <a href="https://github.com/MyKarcio123/OOPlab/blob/main/proj1/src/main/java/agh/ics/oop/Biomes.java">Link</a></li>
<li>A minimap that allows us to keep track of what the distribution of biomes looks like on our map.<a href="https://github.com/MyKarcio123/OOPlab/blob/main/proj1/src/main/java/agh/ics/oop/gui/SimulationController.java">Link</a></li>
<img class="img-fluid" src="../img/darwin/minimap.png">
<img class="img-fluid" src="../img/darwin/terrain.png">
<hr>

<a href="https://github.com/MyKarcio123/OOPlab/tree/main/proj1"><i class="large github icon "></i>Source</a>
