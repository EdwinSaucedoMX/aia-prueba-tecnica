<script setup lang="ts">
import { onMounted, ref } from "vue";
import Card from "./components/Card.vue";

let data = ref([]);

onMounted(() => {
	fetch("/proyectos.json")
		.then((res) => {
			return res.json();
		})
		.then((result) => {
			data.value = result;
			data.value.sort((a: any, b: any) =>
				a.isAvailable < b.isAvailable ? 1 : -1
			);

		});
});
</script>

<template>
  <h1 className="title">Nuestros Proyectos</h1>
  <main className="card-container">
		<div
			className="grid-container"
			v-for="{
				name,
				description,
				location,
				totalArea,
				img,
				terrace,
				rooms,
				isAvailable,
			} in data"
		>
			<Card
				v-bind:name="name"
				v-bind:description="description"
				v-bind:location="location"
				v-bind:totalArea="totalArea"
				v-bind:img="img"
				v-bind:terrace="terrace"
				v-bind:rooms="rooms"
				v-bind:isAvailable="isAvailable"
			/>
		</div>

    
	</main>
</template>
