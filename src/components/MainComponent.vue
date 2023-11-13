<template>
    <div class="wrapper mt-3">
        <h4 class="pt-3 pb-3">alien</h4>
        <div class="row gy-4 bg-white ">
            <div class="col-12 col-md-4 col-lg-3" v-for="(item, index) in store.CardList" :key="index">
                <CardComponent :image="item.card_images.image_url"  :title="item.name"/>
            </div>
        </div>
    </div>
</template>

<script>
import CardComponent from './CardComponent.vue';
import { store } from '../assets/data/store.js';
export default {
    name:'MainComponent',
    components:{
     CardComponent
    },
    data() {
        

        return {
            store
        }
    }
}
</script>

<style lang="scss" scoped>
.wrapper{
    background-color: orange;
}
</style>
