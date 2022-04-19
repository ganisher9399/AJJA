<template>
    <section class="salons">
        <div class="container">
           <Title :sub="subtitle" :title="title"/>
           <p class="text">{{ text }}</p>
           <Button :isLight="true">{{ changeText }}</Button>
        </div>
    </section>
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
            subtitle: 'Не знаете, что вибрати?',
            title: 'Поцетите наши цалони в Моцкбе',
            text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur omnis ipsam voluptates dolorum labore ut eveniet sed cupiditate ex natus autem laborum architecto, numquam fugiat, earum cum voluptatem saepe facilis nemo inventore officia? Possimus recusandae neque, tenetur dolorem sed nisi?',
            btn_text: 'наши цалони',
        }
    },
    computed: {
       changeText(){
          return this.btn_text.toUpperCase()
       }
    }
}
</script>


<style lang="scss">
@import '../../../assets/styles/components/_vars.scss';
@import '../../../assets/styles/components/_mixins.scss';

    .salons{
        width: 100%;
        background: url('../../../assets/images/layout/sec-bg.jpg') no-repeat center / cover;
        padding: 100px 0;
        text-align: center;
        color: $white;
        //media
        @include md{
            padding: 50px 0;
        }


        .text{
            line-height: 25px;
            max-width: 730px;
            margin: 45px auto 60px;
        }
    }
</style>