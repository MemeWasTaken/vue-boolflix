<template>
    <div class="search-bar d-flex align-items-center">
        <input
            id="search"
            class="form-control d-inline-block me-1"
            v-model="textSearch"
            type="text"
            name="search"
            @keypress.enter="$emit('search', textSearch)"
        >
        <button
            class="btn btn-outline-danger ms-1"
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

    .search-bar {

        input {
            height: 34px;
            width: 250px;
        }
    }
</style>