<template>
  <div class="grande">
        <div class="container">
            <CardMovie
                v-for = "objMovie in arrDiscsFiltered"
                :key="objMovie.title"
                :imgUrl="objMovie.poster"
                :title="objMovie.title"
                :author="objMovie.author"
                :year="objMovie.year"
                />
              <div class="artista">made by Alessio Allegrini</div>
          </div>
    </div>
</template>

<script>
import axios from 'axios';
import CardMovie from '@/components/CardMovie.vue';

export default {
  name: 'PageMain',
  components: {
    CardMovie,
  },
  props: {
    genreFilter: String,
  },
  data() {
    return {
      urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
      arrDiscs: null,
    };
  },
  computed: {
    arrGenres() {
      const arrGenres = [];
      if (this.arrDiscs) {
        this.arrDiscs.forEach((objDisc) => {
          if (!arrGenres.includes(objDisc.genre)) {
            arrGenres.push(objDisc.genre);
          }
        });
      }
      // console.log(arrGenres);
      return arrGenres;
    },
    arrDiscsFiltered() {
      if (this.genreFilter === 'all') {
        return this.arrDiscs;
      }
      return this.arrDiscs.filter((objDisc) => objDisc.genre === this.genreFilter);
    },
  },
  watch: {
    arrGenres(newValue) {
      this.$emit('genresReady', newValue);
    },
  },
  created() {
    axios.get(this.urlApi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        this.arrDiscs = axiosResponse.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  flex-wrap: wrap;
  background-color:rgba(30,45,59,255) ;
  height: 80vh;
  .artista {
    color: rgba(30,45,59,255);
  }
  .artista:hover {
      scale: 1.1;
      transition: 1.2s;
      color: white;
    }

}
</style>
