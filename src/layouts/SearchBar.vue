<template>
    <div class="search-bar" :class="{ active: isActive }" >
        <div class="block">
            <i class="fas fa-search"></i>
            <input type="text" placeholder="Search...">
        </div>
        <div class="close-btn" @click="$emit('closeSearchBar')">
            <i class="fas fa-times"></i>
        </div>
    </div>
</template>


<script>
export default {
  props: {
      isActive: {
          type: Boolean,
          default: () => false
      }
  }
}
</script>


<style lang="scss">
@import '../assets/styles/components/_vars.scss';
@import '../assets/styles/components/_mixins.scss';

.search-bar{
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgba($black, $alpha: 0.9);
    z-index: 999999;
    transform: translateY(-100%);
    transition: 0.5s;

    &.active{
       transform: translateY(0%); 
    }


    .block{
        width: 100%;
        max-width: 500px;
        background: $white;
        padding: 10px 20px;
        border-radius: 50px;
        display: flex;
        align-items: center;
        i{
            color: $dark;
            font-size: 20px;
        }
        input{
            width: 100%;
            font-size: 18px;
            color: $dark;
            border: none;
            background: none;
            padding-left: 15px;
        }
    }

    .close-btn{
        margin-left: 30px;
        color: rgba($white, $alpha: 0.7);
        font-size: 25px;
        cursor: pointer;

        &:hover{
            color: rgba($white, $alpha: 1);
            transition: 0.6s cubic-bezier(.5,.06,.9,1.37);
            transform: rotate(270deg);
        }
    }
}    
</style>