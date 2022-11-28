<template>
  <div>
    <!-- collegamento alle altre pagine  -->
    <PageHeader/>
    <MainPage/>
    <FooterPage/>
  </div>
</template>

<script>
// import di tutte le altre pagine 
import PageHeader from '@/components/PageHeader.vue'
import MainPage from '@/components/MainPage.vue'
import FooterPage from '@/components/FooterPage.vue'

export default {
  // disposizione dei compontenti 
  components: {
    PageHeader,
    MainPage,
    FooterPage,
  },
}
</script>


<style lang = "scss">
@import "~bootstrap/scss/bootstrap";
</style>