<template>
	<div id="app">
		<Header
			@userQuery="sendToMain($event)"
		/>
		<Main></Main>
  	</div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

	export default {
		name: "App",
		data() {
			return {
				inquiry: "",
			};
		},
		components: {
			// HelloWorld,
			Header,
			Main,
		},
		methods: {
			sendToMain(text) {
				this.inquiry = text;
				console.log(this.inquiry);
				return this.inquiry
			}
		},
	};
</script>

<style lang="scss">
	@import '~bootstrap/scss/bootstrap.scss';

</style>
