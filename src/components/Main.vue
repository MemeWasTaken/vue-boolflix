<template>
    <main>
        <div v-if="cards.length > 0">
            <Card
                v-for="(card, index) in cards" :key="index"
                :title="card.title"
                :originalTitle="card.original_title"
                :lang="card.original_language"
                :rate="card.vote_average"
            />
        </div>
        <div v-else class="text-white">
            Siamo spiacenti ma la ricerca non ha prodotto nessun risultato
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
            cards: {
                type: Array,
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