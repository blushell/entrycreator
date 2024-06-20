<template>
	<v-card>
		<v-card-title>
			<v-icon>mdi-power-plug</v-icon> Entry.tp Builder
		</v-card-title>
		<v-card-text>
			<plugin-setup @updateData="updateData" />
			<plugin-data :formData="formData" />
		</v-card-text>
	</v-card>
</template>
<script>
export default {};
</script>
<style>
body {
	padding: 2em;
}
.component {
	padding: 25px 0 25px 0;
}
</style>
