<template>
    <section class="email">
      <div class="container">
           <Title :sub="subtitlevido" :title="title" />
           <div class="form">
               <ul>
                   <li><a href=""><i class="fas fa-sign-in"></i>используется кнопка</a></li>
                   <li><a href=""><i class="fas fa-sign-in"></i>используется</a></li>
                   <li><a href=""><i class="fas fa-sign-in"></i>нопка Submit</a></li>
               </ul>
               <form @submit.prevent="sendMail">
                   <input type="text" placeholder="Text......" v-model="message">
                   <Button type="submit">Sends</Button>
               </form>
           </div>
      </div>
    </section>
</template>


<script>
import Title from '@/layouts/Title.vue'
import Button from '@/layouts/Button.vue'

export default {
  components: {
    Title,
    Button,
  },
  data(){
    return{
      subtitlevido: 'формы на сервер используется кнопка Submit',
      title: 'Область не ограничена',
      message: '',
    }
  },
  methods: {
    sendMail(){
        console.log(this.message);
    }
  }     
   
}
</script>


<style lang="scss">
@import '../../../assets/styles/components/_vars.scss';
@import '../../../assets/styles/components/_mixins.scss';
 
 
    .email{
        background: url('../../../assets/images/layout/sec-bg.jpg') no-repeat center / cover;
        color: $white;
        padding: 100px 0;

        .form{
           display: flex;
           justify-content: space-around;
           align-items: center;
           flex-wrap: wrap;
           padding: 70px 0 0 0;
           form{
               background: $white;
               width: 436px;
               height: 85px;
               display: flex;
               justify-content: space-evenly;
               align-items: center;
               input{
                   width: 220px;
                   height: 50px;
                   padding: 0 15px;
                   font-size: 18px;
                   border: 1px solid $border_color;
               }
           }
           ul{
               li{
                   list-style: none;
                   padding: 12px 0;

                   a{
                       color: $bg_color;
                       font-size: 18px;
                       display: flex;
                       justify-content: flex-start;
                       align-items: center;
                       i{
                           margin-right: 14px;
                       }

                   }
               }
           }
        }

    }
</style>