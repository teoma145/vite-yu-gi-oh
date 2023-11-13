<template>
    <div>
        <div class="card bg-transparent border-0 ">
        <img :src="image" :alt="title">
        </div>
    </div>
    
</template>

<script>
export default {
    name:'CardComponent',
    props: [
        'image',
        'title',
        
    ],
    data() {
        

        return {}
    }
}
</script>

<style lang="scss" scoped>

</style>