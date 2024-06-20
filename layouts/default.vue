<template>
	<v-app id="inspire">
		<v-navigation-drawer v-model="drawer">
			<nav>
				<v-list>
					<v-list-item
						v-for="[icon, text, url] in links"
						:key="icon"
						:prepend-icon="icon"
						:title="text"
						:to="url"
						link
					></v-list-item>
				</v-list>
			</nav>
		</v-navigation-drawer>

		<v-app-bar>
			<v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
			<v-app-bar-title>{{ pageTitle }}</v-app-bar-title>
		</v-app-bar>

		<v-main>
			<slot></slot>
		</v-main>
	</v-app>
</template>

<script setup>
const drawer = ref(null);
const route = useRoute();

const links = ref([
	['mdi-home-variant-outline', 'Home', '/'],
	['mdi-toolbox-outline', 'Dev Kits', '/devkits'],
]);

const pageTitle = ref('Application');
watchEffect(() => {
	switch (route.path) {
		default:
			pageTitle.value = 'Home';
			break;
		case '/':
			pageTitle.value = 'Home';
			break;
		case '/devkits':
			pageTitle.value = 'Dev Kits';
			break;
	}
});
</script>
