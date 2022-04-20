<template>
    <div class="home-blog">
       <div class="container">
           <Title :sub="subtitle" :title="title"/>
           <div class="wrapper">
               <BlogCard 
               v-for="item in cutBlogArray" 
               :key="item.id" 
               :title="item.title" 
               :img="item.img" 
               @click="$router.push({name: 'Post', params: {postId: item.id} })"
               />

           </div>
           <Button @click="$router.push({name: 'Blog'})" >{{ btn_text }}</Button>
        </div> 
    </div>
</template>


<script>

import Title from '@/layouts/Title.vue'
import Button from '@/layouts/Button.vue'
import BlogCard from '@/layouts/BlogCard.vue'
import BlogPosts from '@/blog_posts.js'

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
            img: '../../../assets/images/block/r-1.png',
            blog_array: BlogPosts,
       }
    },
    computed: {
       cutBlogArray(){
           return this.blog_array.slice(this.getRandomArray, this.getRandomArray+3);
       },
       getRandomArray(){
           const max = BlogPosts.length - 3
           const min = 0
           return Math.floor(Math.random() * (max - min) + min)
           
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