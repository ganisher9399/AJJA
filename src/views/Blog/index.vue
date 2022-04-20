<template>
   <section class="blogs">
     <div class="block">
           <Title :title='title' :sub='subtitle'/>
     </div>
     <div class="container wrapper">
        <BlogCard 
        v-for="item in blockpost"
        :key="item.id"
        :title="item.title"
        :desc="item.text"
        :img="item.img"
         @click="$router.push({name: 'Post', params: {postId: item.id} })"
        />
     </div>
   </section>
</template>


<script>
import Title from '@/layouts/Title.vue'
import BlogCard from '@/layouts/BlogCard.vue'
import BlogPosts from '@/blog_posts.js'

export default {
  components: {
    Title,
    BlogCard,
  },
  data() {
    return {
      title: 'JEWELLERY BLOG',
      subtitle: 'Articles by Australian designer Simone Walsh',
      blockpost: BlogPosts,
    }
  } 
}
</script>



<style lang="scss">
@import '../../assets/styles/components/_vars.scss';
@import '../../assets/styles/components/_mixins.scss';


.blogs{


    .block{
        // width: 100%;
        // height: 100vh;
        padding: 200px 0;
        color: $white;
        background: url("https://cdn.shopify.com/s/files/1/0021/6592/files/banner-gold-coral-necklace_1600x.jpg?v=1635487500") no-repeat center / cover;
        position: relative;

        &::before{
            content: "";
            position: absolute;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba($black, $alpha: 0.4);
        }
    }
    .wrapper{
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 30px 0;
        flex-wrap: wrap;
        margin: 100px auto;
        //Media
        @include lg{
            margin: 50px auto;
            justify-content: center;
            gap: 25px;
        }
    }
  
}    
</style>