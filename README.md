totality-threejs
===================

A clone of the awesome https://github.com/superguigui/threejs-starter-kit repo, adapted for my use and planned starting structure for totality.
I love this starting setup, as it is very lean compared to most, includes superguigui's torus demo.

![screenshot](/screenshot.png)

## Usage
Clone this repo.

```bash
npm i
```

Launch the main budo livereload server
```bash
npm start
```

For deploying a minified build
```bash
npm run build
```
Place `/index.html` and `/index.js` (+ any used assets) on server.

Clean up (auto lint fix) the code using prettier
```bash
 npm run lint
```

## Features (inherited from the starter)
- ES6 with [Babel](http://babeljs.io)
- [Budo](https://github.com/mattdesl/budo) (browserify local server with livereload)
- [Glslify](https://github.com/glslify/glslify) (browserify transform for glsl)
- Superguigui's personnal [GUI](http://github.com/superguigui/guigui#dev)
- Basic asset preloader (you probably need to extend it for your needs)
- OrbitControls
- Postprocessing with [superguigui's fork](https://github.com/superguigui/Wagner) of [spite's WAGNER](https://github.com/spite/Wagner)

## File Structure and coding style
Object classes are created inside "Objects" directory `src/objects` and contains scene elements.
Objects should try to always extend THREE.Object3D to be addable to a parent (positions, rotation, etc)
They sometimes extend `THREE.Mesh` directly but it may be a bit restrictive (since all geometries, materials etc need to prepared in the constructor before the call to `super()` without being able to use `this`)
Strive to avoid using the `THREE` global keyword and instead import only the Objects needed:

```js
import { Object3D, Mesh, MeshBasicMaterial } from THREE
```

Respect the [Standard](https://standardjs.com) coding style.

