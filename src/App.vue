<template>
	<div id="app">
		<Header
			@userQuery="sendToMain($event)"
		/>
		<Main :cards="cards"></Main>
  	</div>
</template>

<script>
import axios from 'axios';
// import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

	export default {
		name: "App",
		data() {
			return {
				inquiry: "",
				cards: [],
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
				this.getMovies();
				return this.inquiry
			},
			getMovies() {
				axios
					.get(`https://api.themoviedb.org/3/search/movie?api_key=9da47a4b22fa9d371b93ff9409a34189&query=${this.inquiry}`)
					.then((result) => {
						// console.log(result.data.results);
						this.cards = result.data.results;
						// console.log(this.inquiry);
						console.log(this.cards);
					})
					.catch((error) => {
						console.log(error);
					});
			},
		},
	};
</script>

<style lang="scss">
	@import '~bootstrap/scss/bootstrap.scss';
	@import '~mdb-ui-kit/css/mdb.min.css';

</style>
