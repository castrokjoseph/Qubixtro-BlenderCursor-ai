# Qubixtro-BlenderCursor-ai

Watch Tutorial Video ->

download Blender - https://www.blender.org/

download Cursor - https://cursor.com/


Prompt 

"I want you to create a complete Python script for Blender that procedurally turns an existing GLB brain model into a cinematic sci-fi "glass brain with glowing neural connections" visualization.

IMPORTANT:
- Blender is already installed on my computer.
- I already have a GLB brain model downloaded from the internet.
- Do NOT create a new brain mesh from scratch.
- The script must import and use my existing GLB model.
- Make the script easy to configure at the top, especially the GLB file path and output path.
- The entire scene should be generated through Python so I can run the script inside Blender without manually building the scene.
- Use Blender's Python API (bpy).
- Make the script robust and reasonably compatible with modern Blender versions.

==================================================
1. INPUT MODEL
==================================================

Create configuration variables at the top:

GLB_PATH = "PATH_TO_MY_BRAIN.glb"
OUTPUT_PATH = "PATH_TO_OUTPUT"

Import the GLB using Blender's glTF importer.

After importing:
- Detect the imported brain object(s).
- Preserve the original geometry.
- Normalize/scale the model if necessary.
- Center the brain around the world origin.
- Rotate it into a visually appealing orientation.
- Apply transforms where necessary.

The script should not assume the imported object has a specific name.

If the GLB contains multiple mesh objects, identify the brain mesh objects automatically.

==================================================
2. OVERALL VISUAL CONCEPT
==================================================

The final image should look like a futuristic scientific visualization of a human brain.

Concept:

A transparent/translucent glass-like brain floating in a dark environment.

The outer brain should be semi-transparent and elegant rather than looking like ordinary transparent plastic.

Inside the brain, there should be a dense network of glowing neural connections.

Small points of light should travel through these neural connections, suggesting electrical signals moving through neurons.

The visual style should feel:

- cinematic
- futuristic
- scientific
- premium
- mysterious
- high-tech
- slightly cyberpunk
- realistic rather than cartoonish

Think of a visualization of the human brain as a living computational system.

==================================================
3. BRAIN MATERIAL
==================================================

Create a custom material for the brain.

The brain should look like translucent glass / crystal.

Use a physically based shader.

Desired characteristics:

- transparent/translucent outer shell
- subtle glass refraction
- slightly bluish/neutral tint
- low roughness
- realistic specular reflections
- subtle Fresnel effect
- glowing edges when illuminated
- interior remains visible

Do NOT make the brain completely invisible.

The silhouette of the brain must remain clearly readable.

Use a combination of:

- Principled BSDF / Glass BSDF where appropriate
- Transmission
- Fresnel
- subtle emission
- appropriate blend/transmission settings for the Blender version

If pure glass causes problems with Eevee, create a visually convincing approximation using Principled BSDF transmission and emission.

The brain should have slightly brighter edges than its center.

==================================================
4. INTERNAL NEURAL NETWORK
==================================================

This is the most important part.

Create a procedural neural network INSIDE the brain.

The network should consist of:

- hundreds of thin neural connections
- branching curves
- small glowing nodes
- connections between different regions
- varying lengths
- varying thickness
- organic/randomized paths

The network should remain constrained INSIDE the brain.

Do not create random lines floating outside the brain.

Use Blender Curves for the neural connections rather than creating thousands of individual mesh cylinders where possible.

Each neural connection should have:

- very small bevel depth
- emissive material
- slight variation in brightness
- subtle blue/cyan/purple color variation

Create several larger "neural highways" and many smaller branches.

The network should look organic.

Avoid a simple random spaghetti pattern.

Create branching structures resembling biological neurons.

==================================================
5. KEEPING NEURAL NETWORK INSIDE THE BRAIN
==================================================

The neural network must remain inside the brain volume.

Use the imported brain mesh as a spatial boundary.

Possible implementation:

- sample random points around/inside the brain bounding box
- use ray casting / closest point / voxelization / volume checks to determine whether points are inside the brain
- only accept points that are actually inside the brain
- connect accepted points using curves

If accurately determining whether a point is inside the mesh is difficult, use Blender's evaluated mesh / BVH / ray casting approach.

Prioritize visual quality and reliability.

The neural network should follow the general shape of the brain rather than filling a rectangular volume.

==================================================
6. NEURAL NODES
==================================================

Create small glowing spheres at important neural junctions.

Use:

- UV spheres or low-poly spheres
- emission materials
- varying sizes

Some nodes should be brighter than others.

Create a hierarchy:

- major nodes
- secondary nodes
- tiny nodes

The nodes should appear embedded within the brain rather than floating outside it.

==================================================
7. MOVING ELECTRICAL SIGNALS
==================================================

Create visible points of light that travel through the neural connections.

This is very important.

The final visualization should communicate:

"Information is traveling through the brain."

Implement this procedurally.

Possible approach:

- create small emissive spheres
- animate them along selected neural curves
- use drivers/keyframes or Geometry Nodes if appropriate
- create multiple simultaneous signals
- vary their speed
- vary their starting points
- vary their brightness

The signals should look like small pulses of electricity traveling through neural pathways.

Use several signal colors, primarily:

- cyan
- blue
- violet
- white

Avoid making everything equally bright.

Create occasional brighter "bursts" at neural junctions.

==================================================
8. GLOW / BLOOM
==================================================

The neural network should emit a subtle glow.

Use Blender compositor / compositor nodes where appropriate.

Add:

- Glare / Bloom effect
- subtle fog
- light scattering
- atmospheric glow

The glow should be controlled.

Do NOT make the entire image washed out.

The neural connections should have a sharp bright core plus a soft outer halo.

==================================================
9. INTERNAL LIGHTING
==================================================

Add subtle point lights / area lights inside the brain.

These should simulate energy being generated by the neural network.

Use several low-intensity lights.

Some areas of the brain should be brighter than others.

Avoid flat uniform illumination.

==================================================
10. EXTERNAL LIGHTING
==================================================

Create a dark cinematic environment.

Use:

- dark background
- large soft key light
- subtle rim light
- subtle fill light
- blue/cyan/purple accents

The brain should stand out strongly against the background.

Add a subtle rim light around the brain silhouette.

==================================================
11. CAMERA
==================================================

Create a cinematic camera.

The camera should look directly at the brain from a slightly elevated 3/4 angle.

The brain should occupy approximately 60–75% of the frame.

Use a moderate focal length such as:

50mm–85mm

Avoid an extreme wide-angle lens.

Create a shallow cinematic depth of field if appropriate.

Focus should be approximately on the center of the brain.

==================================================
12. COMPOSITION
==================================================

The final composition should be suitable for:

- YouTube thumbnail
- cinematic video
- technology presentation
- AI/software engineering visual
- hero image

Use a 16:9 composition.

Resolution configuration should be easy to change:

RENDER_WIDTH = 1920
RENDER_HEIGHT = 1080

Also allow an optional high-resolution mode such as 3840x2160.

Place the brain slightly off-center if that creates a stronger cinematic composition.

Leave some negative space around the brain.

==================================================
13. BACKGROUND
==================================================

Create a very dark background.

It should not be completely flat black.

Use subtle:

- volumetric haze
- gradients
- faint particles
- very subtle blue/purple atmospheric illumination

Keep the background significantly darker than the brain.

==================================================
14. PARTICLES
==================================================

Optionally create a very small number of floating particles around the brain.

Particles should be:

- tiny
- subtle
- dim
- randomly distributed

They should add depth but should NOT distract from the brain.

==================================================
15. BRAIN SURFACE DETAILS
==================================================

Preserve the original brain folds and geometry.

Do not smooth the brain so much that the anatomical structure disappears.

The gyri and sulci should remain visible through the glass material.

Use lighting and Fresnel effects to emphasize the brain's surface structure.

If useful, create a subtle secondary surface layer or wireframe-like highlight, but keep it elegant.

==================================================
16. MATERIAL COLORS
==================================================

Primary palette:

Brain:
- translucent white
- subtle cool blue

Neural network:
- cyan
- electric blue
- violet
- white

Environment:
- near black
- extremely dark blue/purple

Do not oversaturate the scene.

The brain should feel premium and realistic.

==================================================
17. PERFORMANCE
==================================================

The script must avoid unnecessarily creating thousands of mesh objects.

Prefer:

- Curve objects
- instancing
- particle systems
- Geometry Nodes where useful

Keep the scene performant.

Add configuration variables such as:

NUM_NEURAL_PATHS = 300
NUM_NEURAL_NODES = 150
NUM_SIGNAL_PARTICLES = 30

These should be easy to change.

==================================================
18. RANDOMNESS
==================================================

Use a fixed random seed:

RANDOM_SEED = 42

This ensures that every run produces the same neural network unless I intentionally change the seed.

==================================================
19. RENDER ENGINE
==================================================

Use the best practical Blender render engine available.

Prefer Cycles for the highest-quality final render if the computer can handle it.

However, structure the script so that I can easily switch between:

RENDER_ENGINE = "BLENDER_EEVEE_NEXT"

and

RENDER_ENGINE = "CYCLES"

If Cycles is selected, configure reasonable samples and denoising.

If Eevee is selected, optimize the scene for fast preview rendering.

==================================================
20. ANIMATION
==================================================

Make the scene optionally animated.

Configuration:

ANIMATE_SIGNALS = True
ANIMATION_FRAMES = 240
FPS = 30

The neural signals should move continuously through the neural network.

Also add very subtle variation to:

- neural brightness
- node intensity
- occasional pulses

Do not animate the brain itself aggressively.

The brain should remain stable while information flows through it.

==================================================
21. COMPOSITOR
==================================================

Set up Blender compositor nodes automatically.

Use:

Render Layers
    ↓
Glare
    ↓
Color Balance / subtle contrast
    ↓
Composite

Use a Fog Glow / Glare effect for emissive neural elements.

Keep the glow cinematic rather than excessive.

==================================================
22. OPTIONAL WIREFRAME EDGE EFFECT
==================================================

If technically feasible, create a subtle secondary outline/highlight around the brain.

It should emphasize:

- outer silhouette
- folds
- important surface contours

Do not create a full bright wireframe.

It should be subtle.

==================================================
23. SCRIPT STRUCTURE
==================================================

Organize the Python script into clean functions.

For example:

main()

clear_scene()

import_brain()

normalize_brain()

create_brain_material()

create_neural_network()

create_neural_nodes()

create_signal_animation()

create_environment()

create_lighting()

create_camera()

setup_world()

setup_compositor()

configure_render()

save_blend_file()

render_scene()

Each function should have clear comments.

==================================================
24. IMPORTANT: DEBUGGING
==================================================

Make the script robust.

Print useful information to Blender's console:

- imported objects
- detected brain meshes
- bounding box dimensions
- number of neural paths created
- number of nodes created
- render engine
- output path

If the GLB cannot be imported, print a clear error.

If no mesh is detected after importing, stop with a useful error message.

Do not silently fail.

==================================================
25. OUTPUT
==================================================

The script should:

1. Clear the existing Blender scene.
2. Import my GLB.
3. Prepare the brain.
4. Create the transparent/glass material.
5. Generate the internal neural network.
6. Generate neural nodes.
7. Generate animated electrical signals.
8. Create cinematic lighting.
9. Create the environment.
10. Create the camera.
11. Configure compositor.
12. Configure render settings.
13. Save the .blend file.
14. Render a still image.
15. Save the rendered image to OUTPUT_PATH.

Also make it possible to disable rendering while developing:

RENDER_FINAL = True

==================================================
26. VERY IMPORTANT VISUAL PRIORITY
==================================================

The final result should NOT look like:

- a transparent plastic brain
- random glowing spaghetti
- a basic 3D model with blue lines
- a cartoon
- a generic sci-fi object

It SHOULD look like:

A sophisticated cinematic visualization of a living human brain made from translucent glass/crystal, with an intricate biological neural network glowing inside it and electrical signals continuously traveling through the network.

The outer brain should remain recognizable as a human brain.

The internal neural activity should be the visual focal point.

==================================================
27. DEVELOPMENT MODE
==================================================

Before generating the final high-quality render, create a development mode:

PREVIEW_MODE = True

When PREVIEW_MODE is True:

- lower samples
- fewer neural paths
- fewer nodes
- lower resolution
- faster render

When False:

- use full neural network
- higher samples
- full resolution
- final-quality compositor

==================================================
28. FINAL REQUEST
==================================================

Generate the complete Blender Python script.

Do not give me pseudocode.

Do not omit implementation details.

Make it executable.

Assume that I will save the generated script as:

brain_visualization.py

and execute it using Blender's Python environment.

At the very top of the script, clearly expose all important configuration variables, especially:

GLB_PATH
OUTPUT_PATH
RENDER_ENGINE
RENDER_WIDTH
RENDER_HEIGHT
PREVIEW_MODE
NUM_NEURAL_PATHS
NUM_NEURAL_NODES
NUM_SIGNAL_PARTICLES
ANIMATE_SIGNALS
ANIMATION_FRAMES
RANDOM_SEED
RENDER_FINAL

After generating the script, explain briefly:

1. Where I should put the GLB path.
2. How to run the script in Blender.
3. How to change preview/final quality.
4. How to change the neural density.
5. How to render the animation after the still image works.

Do not ask me to manually build materials, lighting, nodes, or geometry. The Python script should automate the entire setup."
