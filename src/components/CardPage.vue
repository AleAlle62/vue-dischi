<template>
    <!-- creazione card  -->
    <div class="card">
        <div class="text-center">
            <!-- immagine  -->
        <img :src="imgUrl" :alt="title" class="img-fluid" />
        <!-- stampa titolo autore e anno  -->
        <h2 class="name">{{ title }}</h2>
        <div>{{ author }}</div>
        <div>{{ year }}</div>
        </div>
    </div>
</template>

<script>
export default {
    name: "CardPage",
    props: {
    imgUrl: String,
    title: String,
    author: String,
    year: String,
    },
};
</script>

<style lang="scss" scoped>
    .card {
        height: 230px;
        width: 150px;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: rgba(46,58,70,255);
        text-align: center;
        border: 1px solid white ;
        color: white;
        h2 {
            font-size: 15px;
        }
        img {
            height: 100px;
        }
    }
</style>
