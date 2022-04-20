<template>
    <div class="home-blog">
       <div class="container">
           <Title :sub="subtitle" :title="title"/>
           <div class="wrapper">
               <BlogCard title="Hello world for every one hey!" :img="require('@/assets/images/block/r-1.png')" />
               <BlogCard title="Hello world for every one hey!" :img="require('@/assets/images/block/r-2.png')" />
               <BlogCard title="Hello world for every one hey!" :img="require('@/assets/images/block/r-3.png')" />
           </div>
           <Button @click="$router.push({name: 'Blog'})" >{{ btn_text }}</Button>
        </div> 
    </div>
</template>


<script>

import Title from '@/layouts/Title.vue'
import Button from '@/layouts/Button.vue'
import BlogCard from '@/layouts/BlogCard.vue'

export default {
    components: {
        Title,
        Button,
        BlogCard
    },
    data() {
       return {
            subtitle: 'Полезние цтатии',
            title: 'Лучшие цовети по подбору дорогих подарков',
            text: '',
            btn_text: 'читати наш блог',
            img: '../../../assets/images/block/r-1.png'
       }
    }    
}
</script>


<style lang="scss">
@import '../../../assets/styles/components/_vars.scss';
@import '../../../assets/styles/components/_mixins.scss';

.home-blog{
    padding: 120px 0;
    text-align: center;
    // Media
    @include md{
        padding: 50px 0;
    }
    .wrapper{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        padding: 60px 0;
        //Media
        @include lg{
            justify-content: center;
            gap: 30px;
        }
        @include md{
            padding: 30px 0;
        }

    }
}
    
</style>