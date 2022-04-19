<template>
  <div>
    <MainSection />
    <Event />
    <Salons />
    <HomeBlock />
  </div>
</template>


<script>

import MainSection from './components/Main-section.vue'
import Event from './components/Event.vue'
import Salons from './components/Salons.vue'
import HomeBlock from './components/HomeBlock.vue'

export default {
    components: {
        MainSection,
        Event,
        Salons,
        HomeBlock,
    }
}
</script>


<style>
    
</style>