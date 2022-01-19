<template>
    <div class="search">
        <input
            id="search"
            v-model="textSearch"
            type="text"
            name="search"
        >
        <button
            class="btn btn-primary"
            type="submit"
            @click="$emit('search', textSearch)"
            >
            Cerca 
            </button>
    </div>
</template>

<script>
    export default {
        name: "SearchBar",
        data() {
            return {
                textSearch: null,
            };
        },
    }
</script>

<style lang="scss" scoped>
    input {
        height: 34px;
        width: 250px;
    }
</style>