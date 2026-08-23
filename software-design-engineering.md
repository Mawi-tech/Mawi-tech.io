[Back to portfolio home](index.html)

# Artifact One: Software Design and Engineering

**3D Scene Renderer** | C++ and OpenGL
**Origin:** CS-330 Computational Graphics and Visualization, final project

| | |
|---|---|
| **Original artifact** | [View original code](https://github.com/Mawi-tech/CS330) |
| **Enhanced artifact** | [View enhanced code](REPLACE_WITH_ENHANCED_LINK) |
| **Category** | Software Design and Engineering |
| **Course outcomes addressed** | Outcome 3, Outcome 4 |

---

## Describing the Artifact

The artifact I selected for the software design and engineering category is a
3D scene I built in CS-330: Computational Graphics and Visualization, which was
created as a final project for the course. The artifact is a C++ and OpenGL
application that renders my personal office space, including a textured back
wall, desk surface, a Samsung monitor complete with its own stands, a shelf
with supports, and speakers with volume knobs. The scene uses the Phong
lighting model with four distinct light sources, image-based textures, and
reusable meshes that are loaded into memory once and drawn multiple times with
different transformations. To navigate through the scene, the user can move the
camera with WASD and swap to a different view with the P key.

## Justifying Its Inclusion

I chose this artifact because computer graphics can be incredibly complex.
There are multiple complex pieces that must work together to produce a
seamless, navigable scene without degrading performance too much. The scene
allows me to showcase my ability to use appropriate techniques, skills, and
tools to help create a concrete visual goal.

For this enhancement I focused on expanding the scene's complexity, which
aligns with my original plan. I added two new objects to the workspace, a mouse
and a mousepad, positioned on the desk in front of the monitor. Until I can
source better textures for a more realistic depiction of the scene, I
deliberately reuse textures and materials that were already loaded in memory.
This increased the visual complexity of the scene without adding to memory
usage or load time.

## Reflecting on the Enhancement Process

While enhancing the artifact, I ran into software configuration issues. Some
files failed to load because the program could not detect them in the expected
location. I copied the files over and created a new folder so the program could
properly read them. Without that fix, the program would not load the new
objects I had added. This reinforced my understanding of the importance of file
structure and the fragility of relative paths.

This project taught me a valuable lesson about the importance of
well-structured components that are easy to reuse and maintain. The scene
manager file is long, and if every object had been structured differently it
would have been far more difficult to add more objects. Because everything
followed the same predictable pattern, I was able to quickly adjust the
position, material, textures, and transformations of the new objects.

I also made a conscious trade-off in how to model the mouse. Instead of
building an anatomically correct representation, I used a scaled sphere. In a
future iteration I would consider using a half sphere. This illustrates the
trade-off between visual fidelity, implementation effort, and performance.

The main challenge was deceptively simple. When I relocated the project, I
broke the relative paths without realizing it. I saw that all the files were
still intact and assumed they were in the appropriate location, but I was
wrong. Diagnosing the broken relative paths, locating the missing library, and
correcting the folder structure strengthened my debugging and root cause
analysis skills. Those skills tie directly into what I need for backend
development.

## Course Outcomes Met

**Outcome 3: Designing and evaluating computing solutions using algorithmic
principles while managing trade-offs.** I met this outcome by reusing meshes,
textures, and materials instead of loading additional assets. The meshes are
loaded once and reused, so adding a new object adds draw calls rather than
entirely new memory allocations, which keeps the performance cost minimal.

**Outcome 4: Using well-founded techniques, skills, and tools to implement
solutions that accomplish a goal.** I extended the OpenGL rendering pipeline,
applied transformations, textures, and materials correctly, and restored the
broken build configuration. All of that contributed to the goal of a working,
rendered 3D scene of my office.

**Remaining work:** I still want to refactor the code to eliminate magic
constants so the implementation reads more consistently and every value is
explainable.

---

[Back to portfolio home](index.html) | [Next: Algorithms and Data Structures](algorithms-data-structures.html)
