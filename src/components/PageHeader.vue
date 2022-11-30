<template>
    <header>
        <img src="https://storage.googleapis.com/pr-newsroom-wp/1/2018/11/Spotify_Logo_CMYK_Green.png" alt="">
        <label for="select-genres">
        <select
            id="select-genres"
            v-model="genreFilter"
            name="genre"
            @change="genreChange"
        >
            <option value="all">
            All genres
            </option>
            <option
            v-for="genre in genresList"
            :key="genre"
            :value="genre"
            >
            {{ genre }}
            </option>
        </select>
        </label>
    </header>
</template>

<script>
export default {
    name: 'PageHeader',
    props: {
        genresList: Array,
    },
    data() {
        return {
        genreFilter: 'all',
        };
    },
    methods: {
        genreChange() {
        this.$emit('changedGenre', this.genreFilter);
        },
    },
};
</script>

<style lang="scss" scoped>

header {
    background-color: rgba(46,58,70,255);
    display: flex;
    justify-content: space-around;
    align-items: center;
    height: 15vh;
    img {
        height: 50px;
    }
}
</style>
