<template>
 <div>
   <SearchBar :isActive="isSearchBarActive" @closeSearchBar="isSearchBarActive = false" />
   <Navbar @openSearchBar="isSearchBarActive = true"/>
   <router-view />
 </div>
</template>

<script>
import Navbar from "./layouts/Navbar.vue"
import SearchBar from "./layouts/SearchBar.vue"


export default {
  name: 'App',
  components: {
    Navbar,
    SearchBar
  },
  data() {
    return {
      isSearchBarActive: false,
    }
  }
}

</script>

<style lang="scss">
 @import './assets/styles/main.scss';

</style>
