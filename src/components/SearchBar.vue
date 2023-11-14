<template>
    <div>
        <select name="searchbar" id="searchbar" v-model="textSearch" @change="Cardsfilter">
            <option value="">All</option>
            <option :value="archetype.archetype_name" v-for="archetype in store.ArchetypesList">{{ archetype.archetype_name }}</option>
            
        </select>
    </div>
</template>

<script>
  import { store } from '../assets/data/store.js';
  export default {
    name:'SearchBar',
    data () {
        

        return {
            textSearch:'',
            store,
        }
    },
    methods:{
        Cardsfilter(){
            this.$emit('filterChange',this.textSearch)
        }
    }
}
</script>

<style lang="scss" scoped>

</style>