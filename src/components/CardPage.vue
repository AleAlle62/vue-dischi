<template>
    <div class="card">
        <div class="text-center">
        <img :src="imgUrl" :alt="title" class="img-fluid" />
        <h2 class="name">{{ title }}</h2>
        <div>{{ author + genre }}</div>
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
    img{
    width:200px;
    height: 200px;
    }
    .card{
    flex: 1 1 15%;
    background-color: rgb(39, 59, 79);
    text-align: center;
    padding-top:1rem;
    padding-left:.5rem;
    padding-right:.5rem;
    padding-bottom: 4rem;
    }
    h2{
    font-size: 1.2rem;
    color: white;
    text-transform: uppercase;
    padding: .3rem;
    }
    .description{
    color: gray;
    }
</style>
