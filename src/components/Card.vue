<script setup lang="ts">

defineProps({
	name: {
		default: "Nombre no registrado",
		type: String,
	},
	description: {
        default: "Sin descripción",
        type: String,
    },
	location: {
        default: "Ubicación no registrada",
        type:String,
    },
	totalArea: {
        default: -1,
        type: Number,},
	img: {
        default: "/no-image.png",
        type: String,
    },
	terrace: {
        default: -1,
        type: Number,
    },
	rooms: {
        default: -1,
        type: Number,
    },
	isAvailable: {
        default: false,
        type: Boolean,
    },
});
</script>

<template>
    <figure class="card">
        <h3>{{ name }}</h3>
        <p>{{ description }}</p>
        <h4>{{ location }}</h4>
        <span
            ><p>
                {{ `Área Total: ` }}
                {{ totalArea > 0 ? `${totalArea} m2` : "No registrada"}}
            </p>
            <p>
                {{ `Terraza: ` }}
                {{ terrace > 0 ? `${terrace} m2` : "No" }}
            </p>
        </span>
        <h5 class="available" v-if="isAvailable">Disponible</h5>
        <h5 class="unavailable" v-else>No Disponible</h5>
        <img v-bind:src="img">
    </figure>
	

	
</template>

