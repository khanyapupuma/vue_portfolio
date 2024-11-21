<template>
  <div class="container">
    <div class="aboutwrap">
      <div class="row align-items-center">
        <!-- <h1 class="about">About Me</h1> -->
        
          <div v-if="about?.length" class="para">
            <h1 class="about">About Me</h1>


            <p class="par">"Hello! I’m Khanya Pupuma,</p>

            <p class="par">An aspiring Web Developer with a deep-seated passion for technology and a dedicated focus on becoming a full-stack developer.</p>

            <p class="par">My journey through web development is driven by a lifelong fascination with science and technology, motivating me to excel in both back-end and front-end development.</p>

            <p class="par">I am committed to mastering a wide range of technologies and continuously expanding my skill set. This enthusiasm for learning and problem-solving fuels my dedication to delivering high-quality solutions that meet and exceed expectations.</p>

            <p class="par">I thrive on tackling complex challenges and creating innovative, user-centric applications. My goal is to join a dynamic and forward-thinking company where I can contribute my skills and passion while growing as a developer.</p>

            <p class="par">I am eager to collaborate with a team that values professional development and fosters a culture of innovation. With a proactive mindset and a strong work ethic, I look forward to making a meaningful impact and advancing my career in a stimulating and supportive environment."</p>
          </div>
          <Spinner v-else />
      </div>
    </div>
  </div>
</template>
<script setup>
import { computed, onMounted } from "vue";
import { useStore } from "vuex";
import Spinner from "@/components/Spinner.vue";
const store = useStore();
const about = computed(() => store.state.about);
onMounted(() => {
  store.dispatch("fetchAbout");
});
</script>
<style scoped>
@media screen and (max-width: 400px) {
  .row-1 {
    margin-top: 100px;
    display: flex;
    flex-direction: column;
  }
}
h1 {
  text-shadow: 2px 2px 4px rgb(30, 28, 28);
  color: rgb(0, 0, 0);
  font-weight: bold;
  text-align: center; /* Center the heading */
 
}
.details {
  margin-right: 400px;
  margin-top: 60px;
  width: 580px;
}
.col-4{
    margin-bottom: 150px;
}

p {
  font-size: larger;
  width: auto; /* Adjust width for better responsiveness */
  margin-bottom: 20px;
  text-align: center; /* Center the paragraphs */
  display: inline-block; /* Optional: helps center each line */
}

.para{
  margin-left: 180px;
  width: 970px;
}

.aboutwrap {
  margin-top: 150px;
  text-align: center; /* Center-align content */
}
.about {
  margin-bottom: 100px;
}

img {
  border: solid 2px ;
  width: 460px;
  height: 570px;
}
.container {
  margin-left: 100px;
}
img:hover{
  transform: scale(1.01);
}
.par:hover{
  color: rgb(2, 2, 2);
  text-shadow: 4px 4px  8px rgb(255, 255, 255);
}
/* Responsiveness(Mobile) */
@media screen and (max-width: 768px) {
  .container {
    margin: 0 10px;
  }
  .aboutwrap {
    margin-top: 50px;
  }
  .para {
    margin-left: 0;
    width: auto;
  }
  img {
    width: 100%;
    height: auto;
  }
}
</style>
