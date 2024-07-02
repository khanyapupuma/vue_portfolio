<template>
    <div class="wrapper">
    <NavBar/>
  </div>
  
  <router-view/>
</template>
<script>
import NavBar from '@/components/Navbar.vue/'
export default {
      components: {
        NavBar
      }  
}
</script>
<style src="@/assets/Style/style.css">

</style>

