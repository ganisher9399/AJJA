<template>
   <div class="vido-section">
       <div class="container">
          <Title :sub="subtitlevido" :title="title" />
          <div class="play">
      
              <video loop controls>
                <source type="video/mp4" src="http://vjs.zencdn.net/v/oceans.mp4">
              </video>
        
          </div>
       </div>
   </div>
</template>


<script>

import Title from '@/layouts/Title.vue'

export default {
  components: {
    Title,
  },
  data(){
    return{
      subtitlevido: '#ojjo Jovery',
      title: 'Ми в сосиалиних сетях'
    }
  }   
}
</script>


<style lang="scss">
@import '../../../assets/styles/components/_vars.scss';
@import '../../../assets/styles/components/_mixins.scss';

.vido-section{
  width: 100%;


  .play{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    padding: 50px 0 80px;
    video{
      width: 100%;
    }
  }

}
    
</style>