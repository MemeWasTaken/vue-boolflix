<template>
    <header>
        <SearchBar
            @search="formatQuery($event)"
        />
    </header>
</template>

<script>
    // import axios from 'axios';
    import SearchBar from './SearchBar.vue';

    export default {
        name: "Header",
        components: {
            SearchBar,
        },
         data() {
            return {
                textSearch: '',
                // movies: null,
            };
        },
        mounted() {
            // this.getMovies();
        },
        methods: {
            // getMovies() {
            //     axios
            //         .get('https://api.themoviedb.org/3/search/movie?api_key=9da47a4b22fa9d371b93ff9409a34189&query=back')
            //         .then((result) => {
            //             console.log(result.data.results); 
            //             this.movies = result.data.results;
            //         })
            //         .catch((error) => {
            //             console.log(error);
            //         });
            // },
            formatQuery(text) {
                this.textSearch = text.toLowerCase().trim().replace(/\s/g, "+");
                console.log(this.textSearch);
                return this.$emit('userQuery', this.textSearch);
            },
        },
        computed: {

        },
    };
</script>

<style lang="scss" scoped>
    header {
        background-color: #1B1B1B;
        border-bottom: 2px solid #000000;
        width: 100%;
        height: 100px;
    }
</style>