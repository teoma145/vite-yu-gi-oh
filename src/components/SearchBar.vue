<template>
    <div>
        <select name="searchbar" id="searchbar" v-model="textSearch" @change="Cardsfilter">
            <option value="">All</option>
            <option value="Abyss Actor">Abyss Actor</option>
            <option value="Alien">Alien</option>
            <option value="Adamancipator">Adamancipator</option>
        </select>
    </div>
</template>

<script>
export default {
    name:'SearchBar',
    data () {
        

        return {
            textSearch:''
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