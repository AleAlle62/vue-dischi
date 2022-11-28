<template>
    <div class="grande">
        <div class="container">
            <div v-if="arrCard" class="row">
            <CardPage
                v-for = "card in arrCard"
                :key="card.title"
                :imgUrl="card.poster"
                :title="card.title"
                :author="card.author"
                :year="card.year"
                />
            </div>
            <div v-else> caricamento ...</div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import CardPage from '@/components/CardPage.vue';
    export default {
    name: 'MainPage',
    data() {
        return {
        arrCard: null,
        urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
        };
    },
    created() {
        axios.get(this.urlApi)
        .then((axiosResponse) => {
            console.log(axiosResponse.data);
            this.arrCard = axiosResponse.data.response;
        });
    },
    components: {
        CardPage
},
};
</script>

<style lang="scss" scoped>

body {
    background-color:rgba(30,45,59,255) ;
}

.grande {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(30,45,59,255);
    height: 100vh;
}
    .container{

        background-color: rgba(30,45,59,255);
        .row {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 50px;
        }
    }

    
</style>