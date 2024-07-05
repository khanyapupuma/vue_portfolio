<template>
<section class="row" id="home">
<LandingSection/>
</section>
<section class="row" id="about">
  <AboutSection/>
</section>
<section class="row" id="resume" >
<ResumeSection/>
</section>
<section class="row" id="testimonials">
<TestimonialSection/>
</section>
<section class="row" id="reachMe">
  <ContactSection/>
</section>
    
  </template>
  
  <script>
  import LandingSection from '@/components/LandingSection.vue'
  import AboutSection from '@/components/AboutSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import ResumeSection from '@/components/ResumeSection.vue'
import TestimonialSection from '@/components/TestimonialSection.vue'
 export default {
    name: 'NavBar',
    components: {
    LandingSection,
    AboutSection,
    ContactSection,
    ResumeSection,
    TestimonialSection
    }
  }
  </script>
