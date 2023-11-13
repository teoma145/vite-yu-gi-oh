<template>
    <div>
        <div class="card bg-transparent border-0 ">
        <img :src="image" :alt="title">
        <h3>{{ title }}</h3>
        <h4>{{ archetype }}</h4>
        </div>
    </div>
    
</template>

<script>
export default {
    name:'CardComponent',
    props: [
        'image',
        'title',
        'archetype'
        
    ],
    data() {
        

        return {}
    }
}
</script>

<style lang="scss" scoped>

</style>