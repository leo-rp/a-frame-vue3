<script setup>
import 'aframe';
import {GLTFLoader} from 'three/examples/jsm/loaders/GLTFLoader';


const loader = new GLTFLoader();
// src="./assets/logo.svg

</script>

<template>
	<a-scene>
		<a-assets>
			<img id="sky" src="./assets/stars.jpg" />		
		</a-assets>
		
		<a-sky>
			color = "FFFFFF"
			material = "src: #sky"
			rotation = "0 0 0"			
		</a-sky>
	</a-scene>	
</template>