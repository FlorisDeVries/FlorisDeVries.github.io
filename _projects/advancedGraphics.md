---
layout: project
id: advanced_graphics
title: Path Tracer
summary: An expensive, but beautiful render method
platform: C++
logo: assets/images/projects/AdvancedGraphics/PathTracer.png
date: 2019-01-01
start_date: 2018-09-01
end_date: 2018-12-01
---

**Path Tracer** was a challenging and rewarding project completed during my master's course in Advanced Graphics. Building on prior knowledge from earlier graphics courses, this assignment deepened my understanding of rendering techniques and pushed my skills in **C++** and low-level optimization.

### How Path Tracing Works
Path tracing is a rendering technique that simulates light transport by tracing rays of light backward from the camera through each pixel into the scene. Rays interact with surfaces by reflecting, refracting, or absorbing light, accumulating color and light intensity until they either reach a light source or are terminated due to insufficient energy. This approach produces highly realistic images but is computationally expensive.

The process works as follows:
1. **Ray Casting**: Rays are traced backward from the camera, through each pixel, into the scene. Each ray represents a possible path that light could take to reach the camera.
2. **Surface Interaction**: When a ray hits an object, its behavior is determined based on the material properties of the surface. It might reflect, refract, or be absorbed.
3. **Monte Carlo Sampling**: To estimate the illumination at each point, multiple random samples are taken at each interaction to simulate the scattering and bouncing of light. This randomness is what makes Monte Carlo methods powerful but also computationally intensive.
4. **Light Contribution**: Rays accumulate contributions from light sources or ambient light as they bounce around the scene. If a ray encounters a light source directly, its contribution is added to the final pixel color.
5. **Termination**: To prevent infinite bounces, rays are probabilistically terminated using a technique called **Russian Roulette**, which balances computational cost and accuracy.
6. **Pixel Color Computation**: The contributions from all rays for a single pixel are averaged to determine the final color. The more rays that are sampled, the less noisy the result.

While Monte Carlo integration allows path tracing to simulate complex lighting effects with high accuracy, it requires a large number of samples per pixel to reduce noise, making it computationally expensive. Optimizations like **Next Event Estimation** and **Bounding Volume Hierarchies** help improve efficiency.

### Techniques and Optimizations
Over the course of the project, we implemented several techniques to achieve realistic rendering, including:
- **Beer's Law**: Simulated light absorption in transparent materials based on their thickness and color.
- **Refraction**: Accurately modeled how light bends when transitioning between materials with different refractive indices.
- **Texturing and UV Mapping**: Applied textures to objects, which taught me about UV mapping and how to coordinate textures with geometry.
- **Next Event Estimation (NEE)**: Improved sampling efficiency by directly connecting rays to light sources.
- **Russian Roulette**: Reduced unnecessary computations by probabilistically terminating rays with low energy.
- **Bounding Volume Hierarchy (BVH)**: Organized scene geometry hierarchically to accelerate ray-scene intersection tests.
- **Surface Area Heuristic (SAH)**: Optimized the construction of the BVH for better traversal performance.
- **Multi-threading**: Leveraged multi-core CPUs to parallelize ray tracing operations.

### Images and Renders
Below are some of the images generated using our path tracer, showcasing the techniques implemented:

<div class="project-images">
  <img src="/assets/images/projects/AdvancedGraphics/BaseScene.png" alt="Base Scene" />
  <p><b>Base Scene:</b> A simple setup to test reflections, shadows, and primitive rendering.</p>

  <img src="/assets/images/projects/AdvancedGraphics/BeersLaw.png" alt="Beer's Law" />
  <p><b>Beer's Law:</b> Light absorption in a transparent object, showcasing depth-dependent color changes.</p>

  <img src="/assets/images/projects/AdvancedGraphics/Dragon.png" alt="Dragon Model" />
  <p><b>Dragon:</b> A high-poly model demonstrating refraction, shadowing, and texture mapping.</p>

  <img src="/assets/images/projects/AdvancedGraphics/Weird.png" alt="Weird Scene" />
  <p><b>Abstract Scene:</b> An experimental setup to test a variation of different techniques.</p>
</div>

### Outcome
While the project was completed before the release of RTX GPUs, which are optimized for real-time ray tracing, we were able to achieve impressive results on the CPU. The final implementation rendered scenes with complex lighting and materials, producing visually stunning results.

This project not only reinforced my knowledge of computer graphics but also provided hands-on experience in:
- **C++ programming**: Managing pointers and memory for optimal performance.
- **Optimization techniques**: Improving computational efficiency for rendering algorithms.

We received a strong grade for the assignment and were particularly proud of the renders it produced.

**Collaborator**:
- [Niels Mulder](http://www.ncmulder.me)
