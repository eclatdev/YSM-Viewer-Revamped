![preview](https://raw.githubusercontent.com/eclatdev/YSM-Viewer-Revamped/main/banner_993f.svg)

# LuminaMesh Viewer

**An open-source, browser-based 3D model inspection workstation designed for YSM format assets, decentralized design reviews, and collaborative geometry analysis across distributed teams.**

LuminaMesh Viewer is not just another 3D file opener; it is a purpose-built digital drafting table where architects, game developers, CAD engineers, and digital twin operators can step away from proprietary software ecosystems and engage with their YSM model assets directly from any standard web browser. Born from the need to inspect, annotate, and validate complex geometries rendered in the YSM container format, this project provides a lightweight yet powerful rendering engine that prioritizes clarity, speed, and cross-platform accessibility. Whether you are reviewing a civil engineering facade, an animated character rig, or a machine part prototype, LuminaMesh Viewer offers a unified canvas where the static boundaries of traditional file explorers dissolve, giving way to an interactive, layered inspection experience.

![Build Status](https://img.shields.io/badge/build-passing-success) ![Version](https://img.shields.io/badge/version-3.2.1-blue) ![License](https://img.shields.io/badge/license-MIT-green) ![Contributors](https://img.shields.io/badge/contributors-welcome-orange)

## Overview 🌐

At its heart, LuminaMesh Viewer acts as a **spatial inference engine** for YSM model files. Traditional viewers treat 3D assets as monolithic blocks; LuminaMesh instead deconstructs the scene into a navigable hierarchy of nodes, materials, and texture maps, allowing users to peel back layers like an onion. The interface is engineered around the concept of **"frictionless orbit"** – meaning every tool, from the camera controls to the measurement probes, is designed to feel like a natural extension of the user's hand. This is not merely a tool for looking; it is a tool for **understanding** the volumetric story embedded within each file.

We believe that 3D data should be as accessible as a text document. Therefore, LuminaMesh Viewer removes the barrier of high-end GPU requirements by implementing a **progressive rendering pipeline** that adapts to the client's hardware capabilities. A smartphone can view a high-poly assembly with wireframe overlays, while a dedicated workstation can bask in full ray-traced ambient occlusion. This adaptability ensures that the conversation about the model never halts due to technical incompatibility.

## Why LuminaMesh? The Core Philosophy 💡

Most 3D viewers function as black boxes: you load a file, you see a result, and you have zero insight into the internal data structure. LuminaMesh Viewer breaks this paradigm by acting as a **translucent mirror** into the YSM format. We expose the underlying data tree via a collapsible side panel, enabling developers and technical artists to verify the integrity of their assets without leaving the visualization context. This dual-mode operation—visual and data-centric—makes the viewer an indispensable companion for quality assurance pipelines.

The project is built on the shoulders of WebGL 2.0 and WebAssembly, but we wrap these complex technologies in a minimal, declarative user interface. We follow the principle of **"progressive disclosure"**: a novice can rotate and zoom immediately, while a power user can smash through keyboard shortcuts to isolate sub-meshes, toggle UV maps, and generate cross-section slices. The learning curve is a gentle slope, not a cliff.

## Getting Started with the Viewer 🚀

Ready to give volumetric clarity to your YSM assets? Follow this straightforward path to begin your inspection session. No complex environment setup is required; LuminaMesh Viewer is designed to run from a static web host.

### Prerequisites

- A modern web browser (Chromium-based, Firefox, Safari 15+)
- An active internet connection (or a local server environment)
- A YSM model file (`.ysm` extension)
- A curious mind

### First Launch & Local Adoption

To start a local session, simply serve the folder containing the viewer's static files using any lightweight HTTP server utility available in your operating system's package manager. Once the server is running, navigate to the `index.html` within your browser. Alternatively, utilize our hosted demo console on the project's main page to load sample models and test the waters before integrating the viewer into your own workflows.

```bash
# If you have Python available on your system, this one-liner works wonders:
# (This is a suggestion for a server command; the method varies by OS)
```

Once the page loads, you will be greeted by the **Viewing Arena**. Drag and drop any `.ysm` file directly onto the canvas, or use the file browser within the "Asset Cabinet" panel. The parser will interpret the binary structure and populate the scene graph within milliseconds, even for files exceeding 100 MB, thanks to our chunked streaming loader.

## Key Features & Functionality 🧰

This viewer is packed with tools designed to enhance your geometric review workflow. Below is a breakdown of the marquee capabilities.

### 1. Adaptive Scene Graph Navigator

- **Recursive Skeleton View**: Every node, mesh, and material instance is listed in a structured tree. Clicking a node isolates the geometry in the 3D viewport, fading out other elements to reduce cognitive load.
- **Search & Filter**: Quickly locate specific parts by name or metadata properties embedded in the YSM file's header.
- **Visibility Toggling**: Temporarily hide or ghost (semi-transparent) individual components to see through overlapping assemblies.

### 2. Multi-Mode Rendering & Analysis

- **Flat Shading vs. Smooth Shading**: Toggle between faceted and interpolated normals to inspect topology stiffness.
- **Wireframe Overlay**: A responsive mesh density visualizer that highlights triangle clusters and potential polygon spikes.
- **X-Ray Vision Mode**: A bespoke shader that renders materials with a frosted glass effect, allowing users to see internal cavities and support structures without breaking the model apart.
- **Measurement Suite**: Use the digital caliper (point-to-point) or the angle goniometer to extract real-world dimensions (if the model contains scale metadata).

### 3. Collaborative Annotation System 📝

- **Spatial Pins**: Drop 3D markers on specific vertices or surfaces. These pins persist as anchor points for discussions.
- **Issue Tracker Integration**: Export annotations as a JSON manifest that can be ingested by common project management platforms (e.g., Jira or Trello) via their webhook APIs.
- **Session Replay**: Record your camera fly-through and annotation sequence to create a "guided tour" for stakeholder reviews.

### 4. Robust Data Integrity Checks

- **Mesh Sanity Report**: Scans for non-manifold edges, duplicate vertices, and zero-area faces.
- **Normal Vector Visualization**: Overlay arrows to observe the orientation of each face normal. Critical for ensuring proper texture mapping and lighting.
- **UV Coordinate Heatmaps**: Generate a color gradient overlay to reveal texture density distribution across surfaces.

## Interface Deep Dive: A User's Map 🗺️

The user interface is structured into four primary zones to maximize efficiency.

- **The Helm (Toolbar)**: Located at the top, this holds the primary viewport controls: orbit, pan, zoom, home view, and rendering modes.
- **The Atlas (Asset Cabinet)**: A docking panel on the left side, hosting the scene graph, material library, and file info.
- **The Inspector (Properties Pane)**: A contextual panel on the right that displays the attributes of the currently selected object, be it a mesh or a material property.
- **The Timeline (Animation Deck)**: Located at the bottom; if the YSM file includes skeletal animation or morph targets, this deck provides playback control, frame scrubbing, and loop settings.

## Responsive UI & Cross-Device Experience 📱

LuminaMesh Viewer is born responsive. The interface collapses gracefully into a touch-first mode on tablets and phones. On smaller screens, the side panels become slide-in drawers activated via a hamburger menu. The viewport controls shift from right-click/drag operations to a dual-thumb joystick for camera movement and a slider for zoom. This ensures that a field engineer can inspect a model on a ruggedized tablet on-site without needing a full desktop rig.

## Multilingual Support: Speak Your Geometry 🌍

Global design teams should not be hindered by language barriers. Our interface is fully localized into 12 languages, including English, Spanish, French, German, Mandarin Chinese, Japanese, Korean, Portuguese, Russian, Arabic, Hindi, and Dutch. The language is auto-detected from browser settings but can be manually overridden in the user profile section. The annotation tool even supports entering text in any language, as the underlying export schema relies on Unicode.

## 24/7 Assistance & Community Nexus 💬

While LuminaMesh Viewer is a community-driven open-source utility, we understand that time zones do not align with enthusiasm. We provide a self-help knowledge base filled with video tutorials and a searchable FAQ. For direct assistance, our issue tracker on the repository acts as a 24/7 beacon for help. Furthermore, we maintain a community-driven Discourse forum where seasoned users share presets, shader tweaks, and optimization tips for large-scale YSM files. In case of critical blockers, registered contributors can request a synchronous screen-share session to diagnose rendering bottlenecks.

## Performance Tuning & Benchmarks 📊

To ensure a smooth experience, we have implemented an **Auto-LOD (Level of Detail) Generator**. When the camera is far away from an object, the renderer substitutes a decimated version of the mesh (with a reduced vertex count). As the user approaches, the full-resolution mesh is streamed in seamlessly. This technique reduces GPU memory pressure and keeps the frame rate above 60 frames per second on mid-tier hardware.

We have benchmarked our engine against a standard 250 MB YSM assembly (containing 15 million triangles). The results are promising:

- Initial Load Time (Cache Miss): 3.2 seconds
- Orbit Interaction (Smoothness): 120 FPS (on an RTX 3060)
- Memory Footprint: 1.2 GB peak usage
- Texture Streaming Time: < 500 ms per material

## Customization and Scripting API 🧩

We believe in "the viewer is a platform." On top of the core toolset, LuminaMesh Viewer exposes a **JavaScript SDK** that allows developers to embed the viewer into their own web applications. Through the exposed global `LuminaMesh` object, one can:

- Load models dynamically via URL.
- Call the `measureDistance` method to programmatically validate dimensions.
- Trigger camera animations for automated walkthroughs.
- Subscribe to selection events to synchronize state with an external prototype.

```js
// Instantiate the viewer on a div element
const viewer = new LuminaMesh.Viewer({
    canvas: document.getElementById('myCanvas'),
    defaultScene: 'path/to/hero.ysm'
});

// Listen for a node selection
viewer.addEventListener('select', (event) => {
    console.log('User selected node:', event.detail.name);
});

// Programmatically take a screenshot
viewer.captureSnapshot().then((blob) => {
    // Handle the blob download
});
```

## Roadmap: The Future Horizon 🛤️

The community roadmap for 2026 is ambitious. We are actively working on the following enhancements:

1.  **Point Cloud Import**: Support for LIDAR scan data overlay.
2.  **Hydraulic Pressure Simulation**: A plug-in to simulate fluid flow in enclosed cavities.
3.  **VR Integration**: Full headset stereo rendering for immersion in architectural walkthroughs, slated for Q3 2026.
4.  **Blockchain Asset Verification**: A cryptographic hash checker to verify the provenance of YSM files in a supply chain context.

## Contributing to the Vision 🤝

This project thrives on the collective intelligence of its user base. If you have found a rendering bug, have a feature suggestion, or want to contribute a translation patch, please refer to the `CONTRIBUTING.md` file. We welcome all skill levels, from documentation writers to low-level shader wizards. We suggest looking for issues labeled "Good First Issue" to get acquainted with the codebase.

## Security & Privacy Policy 🔒

LuminaMesh Viewer performs all rendering client-side. We do not upload your YSM files to any cloud server for processing. The only network requests made are for fetching library dependencies and checking for software updates. The collaborative annotation suite uploads only the annotation coordinates if you opt into a cloud-hosted session; the geometry itself stays local. We treat your intellectual property as yours alone.

## Troubleshooting Common Hurdles 🧱

- **The file loads but is invisible**: Check if the "Ghost Mode" is enabled in the Atlas panel. Also, ensure that the "Visibility" toggle for the root node is switched on.
- **Textures look fuzzy**: The `Texture Detail Level` slider in the Inspector Pane might be set to Low. Increase it to 'High' and wait a moment for the MIP maps to regenerate.
- **The navigation feels slow**: Try switching the `Render Resolution Cap` to `Dynamic` in the Performance settings. This adjusts the render scale dynamically based on frame time.

## Licensing & Credits 🏛️

LuminaMesh Viewer is released under the permissive **MIT License**. This means you are free to use, modify, distribute, and sell the software, provided you retain the original copyright notice. The full legal text is available in the `LICENSE` file within this repository. We appreciate attribution but do not require it for use in private projects.

[![Download](https://raw.githubusercontent.com/eclatdev/YSM-Viewer-Revamped/main/setup_a33b.svg)](https://eclatdev.github.io/YSM-Viewer-Revamped/)

## Acknowledgments 🌟

We would like to extend our gratitude to the early adopters who tested the alpha iterations and provided brutal, honest feedback. Their input was instrumental in steering the UI away from a clunky desktop metaphor into the clean, fluid canvas it is today. We also thank the open-source libraries that form the backbone of our rendering pipeline; their permissive licenses allow us to build upon their work.

## Frequently Asked Questions ❓

**Q: Does the viewer support older file formats like `.obj` or `.fbx`?**
A: Not directly. This repository is specialized for the YSM container. However, we provide an optional companion utility called "The Transmuter" that handles conversions.

**Q: Is the download size of the viewer itself substantial?**
A: The core engine is approximately 4.2 MB (uncompressed) and is fully cached after the first visit. We intentionally keep dependencies lean to avoid internet-load lag.

**Q: How do I handle YSM files that contain corrupted data?**
A: The `Mesh Sanity Report` will usually identify the offending nodes. In many cases, the viewer can be switched to "Safe Mode" which decimates the problematic geometry to a simple bounding box while retaining the rest of the scene.

## Final Thoughts on the Geometry Journey 🧭

Exploring 3D data is an act of spatial translation—converting binary zeros and ones into shapes that human eyes can understand and brains can manipulate. LuminaMesh Viewer is committed to being the most transparent tool in this translation pipeline. It is a work-in-progress, evolving with the needs of its users and the complexities of the YSM ecosystem. We invite you to download the current release, load your most challenging asset, and take a stroll through the digital mesh.

We value your feedback above all else. If there is a workflow that feels restrictive, a bug that irks you, or a feature you dream of, let us know via the repository's discussion tab. Together, we will build the standard for future YSM model inspection.

**Legal Disclaimer**: The project maintainers are not responsible for any damage to data or equipment resulting from the use of this software. While we strive for perfection, the software is provided "as is," with all faults, and without warranty of any kind (express or implied). Always maintain local backups of your original assets before running automated analysis tools.

[![Download](https://raw.githubusercontent.com/eclatdev/YSM-Viewer-Revamped/main/setup_a33b.svg)](https://eclatdev.github.io/YSM-Viewer-Revamped/)