<template>
  <div>
    <HeaderComponent/>
    
  </div>
  <div>
    <SearchBar  @filter-change="Cardstype"/>
    <MainComponent/>
    <LoadingComponent/>
  </div>
</template>

<script>
  
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue';
  import axios from 'axios';
  import { store } from './assets/data/store.js';
  import LoadingComponent from './components/LoadingComponent.vue'
  import SearchBar from './components/SearchBar.vue'
  

  export default {
    name: 'App',
    components: {
        HeaderComponent,
        MainComponent,
        LoadingComponent,
        SearchBar,
    },
    data() {
    return {
      store,
      
    }
  },
  methods: {

     Cardstype(search) {
      console.log(search);
      if (search) {
        this.params = {
          archetype:search
        }
      } else {
        this.params =null;
      }

      this.getCards();
    },

    getCards() {
      store.error = '';
      const url ='https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0';
      axios.get(url,{params:this.params}).then((response) => {
      store.CardList = response.data.data;
      console.log(store.CardList)
      }).catch((error) => {
        console.log(error)
        this.store.error = error.message;
      })
    },

    getArchetypes(){
      const arcUrl='https://db.ygoprodeck.com/api/v7/archetypes.php';
      axios.get(arcUrl).then((res) => {
      store.ArchetypesList = res.data;
      console.log(store.ArchetypesList)
      })
    }
    },
  
  created() {
    this.getCards();
    this.getArchetypes();
  }
}
    

</script>

<style lang="scss" scoped>

</style>