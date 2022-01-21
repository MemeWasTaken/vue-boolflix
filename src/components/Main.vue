<template>
    <main>
        <div v-if="all.movies.length > 0">
            <Card
                v-for="(movie, index) in all.movies" :key="'movies'+index"
                :image="movie.poster_path"
                :poster="`https://image.tmdb.org/t/p/w342${movie.poster_path}`"
                :title="movie.title"
                :originalTitle="movie.original_title"
                :lang="movie.original_language"
                :rate="movie.vote_average"
            />
        </div>
        <div v-else class="text-white">
            Siamo spiacenti ma la ricerca non ha prodotto film come risultato
        </div>
        <div v-if="all.series.length > 0">
            <Card
                v-for="(serie, index) in all.series" :key="'series'+index"
                :image="serie.poster_path"
                :poster="`https://image.tmdb.org/t/p/w342${serie.poster_path}`"
                :title="serie.name"
                :originalTitle="serie.original_name"
                :lang="serie.original_language"
                :rate="serie.vote_average"
            />
        </div>
        <div v-else class="text-white">
            Siamo spiacenti ma la ricerca non ha prodotto nessuna serie tv risultato
        </div>
    </main>
</template>

<script>
    import Card from "./Card.vue"

    export default {
        name: "Main",
        components: {
            Card,
        },
        data() {
            return {
                
            };
        },
        props: {
            all: {
                type: Object,
                default() {
                    return [];
                },
            },
        },
        mounted() {
            
        },
        methods: {
            
        },
        
    }
</script>

<style lang="scss" scoped>
    main {
        background-color: #434343;
        min-height: calc(100vh - 100px);
        width: 100%;
    }
</style>