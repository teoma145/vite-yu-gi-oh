<template>
    <div class="mywrapper mt-3 p-5">
        <h4 class="pt-1 pb-3 mb-5 ">alien</h4>
        <div class="row gy-4 bg-white ">
          <div class="container">
            <div class="row">
             <div class="bg-black ">
               <h5 class="text-white pt-3 pb-3 text-center ">Found {{ store.CardList.length }} cards</h5>
             </div>
             <div class="mycards mt-2 mb-2" v-for="(item, index) in store.CardList" :key="index">
                <CardComponent :image="item.card_images[0].image_url"  :title="item.name" :archetype="item.archetype"/>
             </div>
            </div>
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
.mywrapper{
    background-color: orange;
}
.mycards{
    width: calc(100% / 5);
}
</style>
