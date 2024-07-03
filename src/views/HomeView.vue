<template>
<section class="row">
<LandingSection/>
</section>
<section class="row">
  <AboutSection/>
</section>
<section class="row">

</section>
<section class="row">

</section>
<section class="row">

</section>
<section class="row">

</section>
    
  </template>
  
  <script>
  import LandingSection from '@/components/LandingSection.vue'
  import AboutSection from '@/components/AboutSection.vue'
 export default {
    name: 'NavBar',
    components: {
    LandingSection,
    AboutSection
     
    }
  }
  </script>
