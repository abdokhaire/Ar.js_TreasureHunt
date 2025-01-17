# Create an Augmented Reality Treasure Hunt using A-Frame & AR.js

## Introduction to Today's Workshop

Use A-Frame & AR.js to create a Augmented Reality Trasure Hunt using HTML, CSS & JavaScript. <br/>

![functional diagram](https://github.com/The-Assembly/Ar.js_TreasureHunt/blob/master/Create-An-AR-Treasure-Hunt.jpg)

## What is WebVR?
WebVR is an experimental JavaScript application programming interface (API) that provides support for virtual reality devices, such as the HTC Vive, Oculus Rift, Google Cardboard or OSVR in a web browser. 
This API is designed with the following goals in mind: <br/>
•	Detect available Virtual Reality devices. <br/>
•	Query the devices capabilities. <br/>
•	Poll the device’s position and orientation. <br/>
•	Display imagery on the device at the appropriate frame rate. <br/>
WebVR makes it possible to experience VR in your browser. The goal is to make it easier for everyone to get into VR experiences, no matter what device you have.
*(https://webvr.info/)*

## What is A-Frame?
 
A-Frame is an open-source web framework for building virtual reality (VR) experiences. It is maintained by developers from Supermedium (Diego Marcos, Kevin Ngo) and Google (Don McCurdy). A-Frame is an entity component system framework for Three.js where developers can create 3D and WebVR scenes using HTML. HTML provides a familiar authoring tool for web developers and designers while incorporating a popular game development pattern used by engines such as Unity.
*(https://aframe.io/)*

## What is AR.js?

AR.js is a JavaScript framework providing an efficient Augmented Reality solution on the Web
acting as a port of AR Toolkit, while leveraging other packages like a-frame and three.js. 

## Markers 
An important feature of AR.js is the possibility to use custom markers, the default type is ‘pattern’. 

AR.js uses artoolkit, and so it is marker based. artoolkit is a software with years of experience doing augmented reality. 
It supports a wide range of markers: multiple types of markers pattern/barcode multiple independent markers at the same time, or multiple markers acting as a single marker, up to you to choose.

Criteria for creating your own marker - <br/>
•	They must be square in shape. <br/>
•	They cannot have white/transparent areas, only black and light grey (e.g. #F0F0F0) <br/>
•	They have to contain simple text, like one letter, a number, or a symbol. <br/>

To create your own markers, go to *(https://jeromeetienne.github.io/AR.js/three.js/examples/marker-training/examples/generator.html)*

Two default markers are – hiro & kanji

![functional diagram](https://github.com/The-Assembly/Ar.js_TreasureHunt/blob/master/hiro.PNG)
![functional diagram](https://github.com/The-Assembly/Ar.js_TreasureHunt/blob/master/kanji.PNG)


## Installation Guide

### Windows
**1. Download Node.js** *(https://nodejs.org/en/)* **(LTS Version Recommended)** <br/>

**2. Open Node.js Command Prompt and type to display versions**
```
 node -v
 npm –v
``` 
 **3. Install obj to gltf converter**
 ```
    npm install -g obj2gltf
 ```
 
### Mac
**1. Install Xcode from App Store or update to the latest version if already installed** *(https://itunes.apple.com/ae/app/xcode/id497799835?mt=12)*

**2. Open Terminal and Install Homebrew** *(https://brew.sh)* **using the following command**
```
  /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
**3. Install node**
```
  brew install node
```
 *Check node & npm version*
 ```
    node -v
    npm -v
 ```
**4. Install obj to gltf converter**
 ```
    npm install -g obj2gltf
 ```
 
## Code
### Include the JS Build
To include A-Frame & AR.js in an HTML file, we drop a <script> tag pointing to the CDN build:
```
<head>
  <script src="https://aframe.io/releases/0.9.2/aframe.min.js"></script>
  <script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.7.1/aframe/build/aframe-ar.js"></script>
</head>
```

To include AR.js, you need to include aframe-ar.js. Then you initialize ar.js in <a-scene>.
```
<a-scene embedded arjs>
```
 
To include AR.js, you need to include aframe-ar.js. Then you initialize ar.js in <a-scene>.
```
<a-scene embedded arjs>
```
 
 Then you tell A-Frame that you want arjs to control the camera. For that, you just add
```
<a-marker-camera preset='hiro'></a-marker-camera>
```
### 1. Default Objects
```
<a-box>/<a-triangle>/<a-ring>/<a-sphere>/<a-tetrahedron>/<a-cylinder>/<a-sphere>

<a-box position='0 0.5 0' scale='0.5 0.5 0.5' rotation='0 0 0' material='color: yellow;'></a-box>
```
### 2.  Using an Image as a Object
```
<a-sphere>

<a-box position='0 0.5 0' scale='0.5 0.5 0.5' rotation='0 0 0' material='color: yellow;' material='opacity: 0.5;'></a-box>
```
**Animation** <br/>
The animation component lets us animate and tween values including: <br/>
•	Component values (e.g., position, visible) <br/>
•	Component property values (e.g., light.intensity) <br/>
We can also tween values directly for better performance versus going through.setAttribute, such as by animating values: <br/>
•	On the object3D (e.g., object3D.position.y, object3D.rotation.z) <br/>
•	Directly within a component (e.g., components.material.material.color, components.text.material.uniforms.opacity.value)
```
<a-animation attribute="scale" dur="2000" from= "0 0 0" to="5 5 5" direction='alternate-reverse' easing= "ease-in-out-circ"  repeat="indefinite"></a-animation>
```
*(https://aframe.io/docs/0.9.0/components/animation.html)*
