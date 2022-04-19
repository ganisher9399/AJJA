<template>
    <div class="home-modal" @click="$emit('action')">
       <div class="modal-card" @click.stop>
          <img :src="itemId.img" alt="image" class="image">
          <div class="content">
            <h3 class="title">{{ itemId.title }}</h3>
            <p class="desc">{{ itemId.desc }}</p>
            <button class="btn" @click="$emit('action')">закрити</button>
          </div>   
        </div> 
    </div>
</template>


<script>
import Collection from '@/collection.js'
export default {
   props: {
      itemId: Object,
   }, 

}
</script>


<style lang="scss">
@import '../../../assets/styles/components/_vars.scss';
@import '../../../assets/styles/components/_mixins.scss';

    .home-modal{
      position: fixed;  
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background: rgba($black, $alpha: 0.8);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 9999;

      .modal-card{
        background: $white;
        width: 50%;
        height: 90vh;
        //media
        @include xl{
            width: 70%;
        }
        @include md{
            width: 90%;
        }
        img{
          width: 100%;
          height: 400px;
          object-fit: cover;
          //Media
          @include sm{
            height: 250px;
          }
        }

        .content{
          width: 100%;
          padding: 30px;

          .title{
            font-size: 30px;
            margin: 15px 0;
            text-transform: uppercase;
          }
          .desc{
            font-size: 17px;
            font-family: sans-serif;
            font-weight: 500;
            padding: 20px 0;
           }

          .btn{
              padding: 15px 30px;
              background: $dark;
              color: $white;
              border-radius: 10px;
              font-weight: 500;
              font-size: 18px;
          }
        }
        

      }
    }
</style>