---
layout: project
id: graphics
title: Ray Tracer
summary: First basic ray tracer
platform: C#, OpenTK
logo: assets/images/projects/Graphics/Graphics.png
date: 2016-06-01
start_date: 2016-04-01
end_date: 2016-06-01
---

The "Ray Tracer" project was an assignment for our first Graphics course, where we explored and experimented with different rendering techniques. Over the course of two months, we developed a program that simulated the behavior of light rays to render a 3D scene, using a method called **ray tracing**.

The challenge lay in getting the mathematical model to work correctly. This involved simulating "light" rays in reverse: sending a ray through each pixel of the screen and tracing its path until it either reached a light source or was extinguished after too many bounces. 

For this assignment, we implemented the following key techniques:
- **Primitive shapes**: Rendering basic geometric shapes such as spheres and planes.
- **Reflection and refraction**: Simulating how light interacts with transparent and reflective surfaces.
- **Shadows**: Casting realistic shadows from objects within the scene.
- **Skydome**: Adding an environment map to provide background and ambient lighting.

While the performance of this ray tracer was typical for a first attempt, with minimal optimizations, it was a visually rewarding experience. This project also laid the foundation for future explorations into rendering techniques.

The project was completed in collaboration with:
- [Niels Mulder](http://www.ncmulder.me)
- [Marijn Suijten](https://github.com/MarijnS95)
