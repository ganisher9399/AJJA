<template>
   <section class="event">
       <div class="container">
           <Title :sub="subtitle" :title="title" />

           <div class="btns-wrapper">
                <button 
                v-for="(item, idx) in collection"
                :key="item.id"
                class="btn"
                :class="{ active: toButton === idx }"
                @click="toButton = idx"
                
                
                >
                
                 <span>  {{ item.ctg_name.text }}</span>
                </button>
           </div>


           <div class="cards-wrapper">
               <div 
               class="card" 
               v-for="item in collection[toButton].data"
               :key="item.product_id"
               @click="isOpen = item"
               
               >
                   <img :src="item.img" :alt="item.title">
                   <h3 class="title">{{ item.title }}</h3>
               </div>
           </div>

            <HomeModal
            v-if="isOpen"
            @action="isOpen=false"
            :itemId="isOpen"
            />

       </div>
   
   </section>
</template>


<script>
import Title from '../../../layouts/Title.vue'
import Collection from '@/collection.js'
import HomeModal from './HomeModal.vue'

export default {
    components: {
        Title,
        HomeModal,
    },
    data(){
        return {
          toButton: 0,  
          subtitle: 'К мероприятиям',
          title: 'Нацтояшая красота здеси!',
          collection: Collection,
          isOpen: false,
        }
    }
}
</script>



<style lang="scss">
@import '../../../assets/styles/Pages/Home/Event-section.scss'
    
</style>