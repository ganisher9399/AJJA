<template>
  <div>
    <MainSection />
    <Event />
    <Salons />
    <HomeBlock />
    <VidoPlear />
    <SendMail />
  </div>
</template>


<script>

import MainSection from './components/Main-section.vue'
import Event from './components/Event.vue'
import Salons from './components/Salons.vue'
import HomeBlock from './components/HomeBlock.vue'
import VidoPlear from './components/VidoPlear.vue'
import SendMail from './components/SendMail.vue'

export default {
    components: {
        MainSection,
        Event,
        Salons,
        HomeBlock,
        VidoPlear,
        SendMail,
    }
}
</script>


<style>
    
</style>