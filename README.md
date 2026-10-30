# BrainScan

An interactive 3D brain explorer that runs entirely in the browser. Rotate the model, click a region, and learn what it does, what happens if it's damaged, and how it connects to other regions.

**[Live demo](https://n-wilson2001.github.io/BrainScan/)**

## Features

- **20 explorable regions**, from the frontal lobe to the medulla, each with its functions, effects of damage, and a fun fact
- **X-ray mode** to see the structures hidden inside the brain
- **Exploded view** that pulls the parts apart
- **Search** by region or function, such as "memory" or "balance"
- **Touch support** with a phone layout that keeps the brain pinned above the info panel

## How it works

- **Rendering:** Three.js with WebGL, plus a bloom pass for the neon glow
- **Geometry:** the cortex is generated procedurally, using Perlin noise to form the folds rather than a pre-made 3D model
- **Shading:** custom GLSL draws sharp region borders and fold detail per pixel, at any zoom level
- **Interaction:** a bounding-volume hierarchy (`three-mesh-bvh`) keeps hover and click fast on the detailed mesh
- **Animation:** a JavaScript `requestAnimationFrame` loop drives the rotation, camera moves, and transitions

## Built with Claude

I built this with Claude as an AI development partner. The app itself doesn't call Claude or any other AI service while it runs.

## Run it locally

There's no build step, but the browser needs a local server to load the JavaScript modules:

```bash
python -m http.server 5173
```

Then open http://localhost:5173. An internet connection is required, because Three.js loads from a CDN.

## Project structure

```
index.html       Page layout and dependency import map
css/styles.css   Styles
js/regions.js    Region content and colors
js/main.js       3D scene, geometry, shaders, and interaction
```

This project is for education and exploration. The model is a stylized illustration, not a medical reference.
