---
layout: project
id: compute_shaders
title: Compute Shaders
summary: A more optimized Path and Ray tracer in Unity
platform: Unity
logo: assets/images/projects/ComputeShaders/niceRender.png
date: 2021-06-01
start_date: 2021-04-01
end_date: 2021-06-01
---

The **Compute Shaders** project was a personal exploration into optimizing rendering techniques, specifically ray and path tracing, using Unity. Building on my knowledge from the *Advanced Graphics* course, this project allowed me to dive deeper into **compute shaders** and their potential for GPU acceleration.

### Project Overview
To get started, I followed [this comprehensive tutorial](https://www.gamedeveloper.com/programming/gpu-ray-tracing-in-unity-part-1) on implementing ray and path tracing in Unity. After completing the tutorial, I expanded upon the initial framework to include additional techniques and features:
- **Beer's Law**: Simulated light absorption for realistic rendering of transparent objects.
- **Reflections and Refractions**: Enhanced light behavior at material boundaries.
- **Skybox Integration**: Added a skybox for realistic environmental lighting.
- **Improved Scene Structure**: Organized the Unity project with **scriptable objects** to allow easy swapping of scenes and rendering techniques.

### Key Learnings
This project taught me valuable lessons in Unity and rendering techniques, including:
- **Compute Shaders**: Leveraged the GPU for parallelized ray and path tracing, achieving significant performance improvements compared to CPU-based methods.
- **Scriptable Objects**: Simplified data management in Unity, making the project more modular and scalable.
- **Rendering Optimization**: Applied concepts from my *Advanced Graphics* course to create a more efficient and visually stunning implementation.

### Screenshots and Renders
Below are some renders showcasing the capabilities of the ray and path tracers:

<div class="project-images">
  <img src="/assets/images/projects/ComputeShaders/render2.png" alt="Path Tracer - Scene 1" />
  <p><b>Path Tracer (Scene 1):</b> Demonstrates realistic lighting, reflections, and refraction.</p>

  <img src="/assets/images/projects/ComputeShaders/render4.png" alt="Ray Tracer - Scene 1" />
  <p><b>Ray Tracer (Scene 1):</b> Highlights the difference in rendering techniques for the same scene.</p>

  <img src="/assets/images/projects/ComputeShaders/render3.png" alt="Path Tracer - Scene 2" />
  <p><b>Path Tracer (Scene 2):</b> A different perspective showing complex material interactions.</p>
</div>

### Future Plans
While this project is complete for now, it serves as a solid foundation for further experimentation. I may revisit it in the future to explore additional features, optimizations, and rendering techniques.

### Additional Resources
If you’re interested in learning more about Unity and compute shaders, I recommend:
- The [Ray and Path Tracing Tutorial](https://www.gamedeveloper.com/programming/gpu-ray-tracing-in-unity-part-1).
- The excellent resources available at [Catlike Coding](https://catlikecoding.com/unity/tutorials/).

You can find the source code for this project on [GitHub](https://github.com/FlorisDeVries/TracersComputeShaders).
