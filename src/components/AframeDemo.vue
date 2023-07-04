<script setup>
import 'aframe';
import {GLTFLoader} from 'three/examples/jsm/loaders/GLTFLoader';
import sky from '@/assets/stars.jpg'
import mountain from '@/assets/models/mountain.glb';



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
			color= "#e2e2e2"
			material="src: #sky"
			rotation = "0 0 0"
		/>

		<a-entity id="mountain" position="0 0 0" scale="10 10 10"/>
	</a-scene>	
</template>