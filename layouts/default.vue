<template>
	<v-app id="inspire">
		<v-navigation-drawer v-model="drawer">
			<nav>
				<ul>
					<li><NuxtLink to="/index">Home</NuxtLink></li>
					<li><NuxtLink to="/devkits">Dev Kits</NuxtLink></li>
				</ul>
			</nav>
		</v-navigation-drawer>

		<v-app-bar>
			<v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

			<v-app-bar-title>Application</v-app-bar-title>
		</v-app-bar>

		<v-main>
			<slot></slot>
		</v-main>
	</v-app>
</template>

<script setup>
import { ref } from 'vue';

const drawer = ref(null);
</script>

<script>
export default {
	data: () => ({ drawer: null }),
};
</script>
