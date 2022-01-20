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
                
            };
        },
        mounted() {
            
        },
        methods: {
            formatQuery(text) {
                this.textSearch = text.toLowerCase().trim().replace(/\s/g, "+");
                // console.log(this.textSearch);
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