<template>
    <div class="blog-card" :style="{ backgroundImage: `url(${img})`}" >
        <h3 class="title">{{ title }}</h3>
    </div>
</template>


<script>
export default {
 props: {
    title: String,
    img: String,
 }
}
</script>



<style lang="scss">
@import '../assets/styles/components/_vars.scss';
@import '../assets/styles/components/_mixins.scss'; 
 

.blog-card{
    width: 350px;
    height: 370px;
    padding: 35px;
    display: flex;
    justify-content: center;
    align-items: flex-end;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    cursor: pointer;
    background-color: #ececec;
    //media
    @include xl{
       width: 290px;
       height: 310px;
    }

    .title{
        max-width: 210px;
        text-align: center;
        font-size: 21px;
        line-height: 30px;
        color: $white;
        font-weight: 400;
    }
}    
</style>