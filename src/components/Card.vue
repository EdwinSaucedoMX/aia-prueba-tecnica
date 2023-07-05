<script setup lang="ts">
import AreaIcon from "/area.svg";
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
		type: String,
	},
	totalArea: {
		default: -1,
		type: Number,
	},
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
		<section v-bind:class="'head'">
			<h3>{{ name }}</h3>
			<section class="row-container">
				<p>{{ description }}</p>
				<span><object width="25px" data="/location.svg"></object>{{ location }}</span>
			</section>
		</section>
		<section v-bind:class="'tail'"
			>
            <p>
                <object width="25px" data="/area.svg"></object>
				{{ totalArea > 0 ? `${totalArea} M` : "No registrada" }}
			</p>
			<p>
                <object width="25px" data="/terrace.svg"></object>
				{{ terrace > 0 ? `${terrace} M` : "No" }}
			</p>
			<p>
                <object width="25px" data="/room.svg"></object>
				{{ rooms > 0 ? `${rooms}` : "No registrado" }}
			</p>
		</section>
		<section class="is-available">
			<h5
				class="available"
				v-if="isAvailable"
			>
				En venta
			</h5>
			<h5
				class="unavailable"
				v-else
			>
				Vendido
			</h5>
		</section>
        <img v-bind:src="img" />
	</figure>
</template>
