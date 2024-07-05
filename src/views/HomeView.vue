<template>
<section class="row">
<LandingSection/>
</section>
<section class="row">
  <AboutSection/>
</section>
<section class="row">
<ResumeSection/>
</section>
<section class="row">

</section>
<section class="row">

</section>
<section class="row">
  <ContactSection/>
</section>
    
  </template>
  
  <script>
  import LandingSection from '@/components/LandingSection.vue'
  import AboutSection from '@/components/AboutSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import ResumeSection from '@/components/ResumeSection.vue'
 export default {
    name: 'NavBar',
    components: {
    LandingSection,
    AboutSection,
    ContactSection,
    ResumeSection 
    }
  }
  </script>
