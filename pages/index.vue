<template lang="pug">
.main
  Header
  HeroBlock
  AboutUs
  Services
  Scheme
  .floating-button
    a(href="tel:+79888712021" target="_blank")
      img(src="~/assets/images/phone.svg" style="width: 60px;") 
  .floating-button.wats
    a(href="https://wa.me/79888712021" target="_blank")
      img(src="~/assets/images/whats.svg") 
</template>

<script>
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage'
})
</script>

<style lang="scss">
.main{
  position: relative;
  .floating-button{
    position: fixed;
    bottom: 20px;
    right: 20px;
    z-index: 100;
   &.wats{
    bottom: 100px
   }
  }
}
h1, h2{
  font-size: 24px;
  @media(min-width: 992px){
    font-size: 32px;
  }
}


</style>
