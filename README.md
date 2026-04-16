# Realtime Cascades is a game engine that combines:

- A modern Vulkan renderer
- A runtime/editor workflow for rapid iteration
- Hot-reloadable game/shader logic in development builds
- A practical scene pipeline around glTF assets

## Features

### Rendering Pipeline

- Vulkan 1.4 renderer using dynamic rendering and synchronization2
- Graphics pipeline library workflow for modular pipeline creation
- Forward+ tiled lighting path with per-tile light index/list buffers
- Hardware-adaptive shader variant selection for FP16 and ray-query capability
- Opaque geometry through GPU-driven indirect multi-draw flow
- Transparent geometry rendered with distance sorting for correct blending
- Optional depth prepass path used for tighter culling and stable lighting
- Skybox/IBL pipeline with equirectangular-to-cubemap conversion, irradiance convolution, prefiltered environment, and BRDF LUT generation
- Runtime tone mapping modes including Reinhard, ACES, Uncharted2, and HGIG behavior in HDR10 mode
- Bindless megabuffers data driven memory architecture
- GPU Skinning for animations

### Visibility, Culling, and LOD

- Compute-driven frustum culling and indirect command generation
- Hi-Z depth pyramid generation and occlusion culling path
- Multiple Hi-Z debug sub-modes for visibility state, mip heatmaps, and sampling comparison
- Forward+ tile diagnostics including tile grid and light count heatmaps
- Automatic mesh LOD chain generation with meshoptimizer

### Lighting, Shadows, and Ray Features

- Cascaded directional shadow maps with runtime resolution controls
- Point and spot local shadow map support
- Ray-traced shadows on capable GPUs using TLAS/BLAS data
- Ray-traced one-bounce diffuse GI with adjustable max ray distance
- Ray-traced specular reflections with adjustable max ray distance
- Runtime shadow mode switching and shadow master toggle

### Image Quality and Display

- Temporal anti-aliasing with jitter, motion vectors, and history resolve
- Per-frame TAA history validity management and reset handling on state changes
- HDR capability probing and runtime mode management (SDR, scRGB, HDR10 static path)
- Exposure controls with auto mode and manual EV100 override
- Runtime HDR/tone-mapping debug logging and status reporting

### Game, Assets, Scene, and Animation

- glTF loading pipeline for meshes, materials, textures, skins, and animations
- Runtime model spawning requests and completion reporting
- Skybox HDR environment swapping at runtime
- Texture decode and optional downscaling during asset ingest
- Model, skeleton, and animation caching paths to reduce repeated load costs
- Scene-level toggles for TAA, GI, specular, shadows, depth prepass, and light culling
- Data driven ECS in the game layer
- Multithreaded job system with lock-free queues, work stealing

## Demo

Full-quality capture (original export):

[Download Vulkan-GameEngine.mp4](https://github.com/John-Giskhan/Cascades/releases/latest/download/Vulkan-GameEngine.mp4)
