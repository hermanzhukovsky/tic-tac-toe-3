<template>
	<hello-world></hello-world>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import { mapGetters, mapMutations } from 'vuex';
export default {
	name: "App",
	components: {
		HelloWorld,
	},
	computed: mapGetters(['mode']),
	methods: {
		...mapMutations(['updateSquares']),
		onStorageUpdate(e) {
			if (e.key === 'history') {
				this.updateSquares();
			}
		}
	},
	created() {
		if (this.mode === 'multiplayer') {
			this.$store.dispatch('initMultiplayerMode')
		}
	},
	mounted() {
		window.addEventListener('storage', this.onStorageUpdate)
	}
};
</script>

<style lang="scss">
</style>
