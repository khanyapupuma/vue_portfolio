<template class="dom">
    <div class="wrapper">
    <NavBar/>
  <main class="container-fluid">
    <router-view/>
  </main>
  <Footer/>
  </div>
</template>
<script>
import NavBar from '@/components/Navbar.vue/'
import Footer from '@/components/Footer.vue'
export default {
      components: {
        NavBar, Footer
      }  
}
</script>
<style src="@/assets/Style/style.css">

</style>

