<template>
    <div v-if="store.CardList.length < 1">
     <h1 class="text-bg-dark text-center">Ricerca Carte</h1>
    </div>
</template>

<script>
   import { store } from '../assets/data/store.js';
    export default {
        name:'LoadingComponent',
    
    data() {
        return {
            store
        };
    },
    }
</script>

<style lang="scss" scoped>

</style>