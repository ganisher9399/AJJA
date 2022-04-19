<template>
    <div class="home-blog">
       <div class="container">
           <Title :sub="subtitle" :title="title"/>
           <Button>{{ btn_text }}</Button>
        </div> 
    </div>
</template>


<script>

import Title from '@/layouts/Title.vue'
import Button from '@/layouts/Button.vue'

export default {
    components: {
        Title,
        Button
    },
    data() {
       return {
            subtitle: 'Полезние цтатии',
            title: 'Лучшие цовети по подбору дорогих подарков',
            text: '',
            btn_text: 'читати наш блог',
       }
    }    
}
</script>


<style lang="scss">
@import '../../../assets/styles/components/_vars.scss';
@import '../../../assets/styles/components/_mixins.scss';

.home-blog{
    padding: 120px 0;
    // Media
    @include md{
        padding: 50px 0;
    }
}
    
</style>