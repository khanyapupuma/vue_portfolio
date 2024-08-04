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
<section class="row" id="project">
<ProjectsSection/>
</section>
<section class="row" id="tools">
<ToolsSection/>
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
import ProjectsSection from '@/components/ProjectsSection.vue'
import TestimonialSection from '@/components/TestimonialSection.vue'
import ToolsSection from '@/components/ToolsSection.vue'
 export default {
    name: 'NavBar',
    components: {
    LandingSection,
    AboutSection,
    ContactSection,
    ResumeSection,
    TestimonialSection,
    ProjectsSection,
    ToolsSection
    }
  }
  </script>
