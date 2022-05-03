three.js
========
# ThreeIPFS
The ThreeIPFS project is the Three.js javascript code library integrated into IPFS. With Three.js, 3D objects can be published on the Web. Thanks to this integration, a 3D object can be hosted in IPFS. This module can be used in projects such as 3D NFT.

# Stages

✅ The Three.js JavaScript library has been forked. <br>
⌛️Integration of Three.js to use external objects <br>
⏳Adapting remote modeling to IPFS.<br>
⏳Developing a module for use in open source content management systems.<br>


Integrator Developer:
Excelsior Hiekzen

### Usage ###

This code creates a scene, a camera, and a geometric cube, and it adds the cube to the scene. It then creates a `WebGL` renderer for the scene and camera, and it adds that viewport to the `document.body` element. Finally, it animates the cube within the scene for the camera.

```javascript
import * as THREE from 'three';

// init

const camera = new THREE.PerspectiveCamera( 70, window.innerWidth / window.innerHeight, 0.01, 10 );
camera.position.z = 1;

const scene = new THREE.Scene();

const geometry = new THREE.BoxGeometry( 0.2, 0.2, 0.2 );
const material = new THREE.MeshNormalMaterial();

const mesh = new THREE.Mesh( geometry, material );
scene.add( mesh );

const renderer = new THREE.WebGLRenderer( { antialias: true } );
renderer.setSize( window.innerWidth, window.innerHeight );
renderer.setAnimationLoop( animation );
document.body.appendChild( renderer.domElement );

// animation

function animation( time ) {

	mesh.rotation.x = time / 2000;
	mesh.rotation.y = time / 1000;

	renderer.render( scene, camera );

}
```

If everything went well, you should see [this](https://jsfiddle.net/7u84j6kp/).

### Cloning this repository ###

Cloning the repo with all its history results in a ~2 GB download. If you don't need the whole history you can use the `depth` parameter to significantly reduce download size.

```sh
git clone --depth=1 https://github.com/hiekxel/three.js.git
```

### Change log ###

[Releases](https://github.com/hiekxel/three.js/releases)

