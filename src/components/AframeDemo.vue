<script setup>
import 'aframe';
import {GLTFLoader} from 'three/examples/jsm/loaders/GLTFLoader';
import sky from '@/assets/stars.jpg'
import mountain from '@/assets/models/mountain.glb';

import RocketComponent from './RocketComponent.vue';



const loader = new GLTFLoader();
loader.load(mountain, (d) => {
	const entity = document.getElementById("mountain");
	entity.object3D.add(d.scene);
});

</script>

<template>
	<a-scene>
		<a-assets>
			<img id="sky" :src="sky"/>
		</a-assets>
		
		<a-sky
			color= "#ffffff"
			material="src: #sky"
			rotation = "0 0 0"
		/>

		<a-entity id="mountain" position="0 0 0" scale="15 15 15"/>
		<RocketComponent x="0" y="50" z="-80" />
	</a-scene>	
</template>