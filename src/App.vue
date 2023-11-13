<template>
  <div>
    <HeaderComponent/>
    
  </div>
  <div>
    <MainComponent/>
  </div>
</template>

<script>
  
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue';
  import axios from 'axios';
  import { store } from './assets/data/store.js';

  export default {
    name: 'App',
    components: {
        HeaderComponent,
        MainComponent,
        
    },
    data() {
    return {
      store
    }
  },
  methods: {
    getCards() {
      const url ='https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0';
      axios.get(url).then((response) => {
      store.CardList = response.data.data;
      })
    }
    },
  
  created() {
    this.getCards();
  }
}
    

</script>

<style lang="scss" scoped>

</style>