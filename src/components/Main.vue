<template>
    <main>
    </main>
</template>

<script>
    import axios from 'axios';

    export default {
        name: "Main",
        data() {
            return {
                tryout: "all",
                movies: null,
            };
        },
        methods: {
            getMovies() {
                axios
                    .get(`https://api.themoviedb.org/3/search/movie?api_key=9da47a4b22fa9d371b93ff9409a34189&query=${this.tryout}`)
                    .then((result) => {
                        console.log(result.data.results);
                    })
                    .catch((error) => {
                        console.log(error);
                    });
            },
        },
        
    }
</script>

<style lang="scss" scoped>
    main {
        background-color: #434343;
        width: 100%;
        height: calc(100vh - 100px);
    }
</style>