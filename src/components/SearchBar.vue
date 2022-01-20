<template>
    <div class="search">
        <input
            id="search"
            class="form-control d-inline-block"
            v-model="textSearch"
            type="text"
            name="search"
        >
        <button
            class="btn btn-outline-danger"
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