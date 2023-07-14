<script setup>
import { onMounted } from 'vue'
import 'aframe';
import {GLTFLoader} from 'three/examples/jsm/loaders/GLTFLoader';
import rocketModel from '@/assets/models/rocket.glb';

const props = defineProps({
	x: Number,
	y: Number,
	z: Number
})

const loader = new GLTFLoader();
loader.load(rocketModel, (d) => {
	const entity = document.getElementById("rocket");
	entity.object3D.add(d.scene);
});


</script>
<template>
	<a-entity id="rocket" :position="`${props.x} ${props.y} ${props.z}`" scale="15 15 15"
		animation="property:rotation.y;from:0;to:360; dur:2000;dir:normal;loop:true;easing:linear;"
	/>
</template>