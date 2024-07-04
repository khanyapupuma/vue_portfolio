<template>
    <div class="container">
      <div class="row">
          <h1>About Me</h1>
      </div>
      <div class="row-1">
        <div class="col-4">
              <img src="https://khanyapupuma.github.io/all-images/all-images/Images/20240422_094850.jpg" alt="home-pic" class="img-fluid w-75 shadow rounded-top" loading="lazy">
          </div>
      <div class="details">
          <div v-if="about?.length">
              <!-- <p class="lead" v-for="(ele,index) in data" :key="index">
                  {{ ele.Name }}
              </p> -->
              <p class="lead" >
                <span class="fname">Name: {{ info.name }}</span>
                <span class="intro">Intro: {{ info.intro }}</span>
                <span class="values">Interest: {{ info.interest }}</span>
              </p>
              </div>
          <Spinner v-else/>
      </div>
      </div>
    </div>
  </template>
  <script setup>
  import { computed, onMounted} from 'vue'
  import {useStore} from 'vuex'
  import Spinner from '@/components/Spinner.vue'
import { ref } from 'vue';
  const store = useStore()
  const about = computed(() => store.state.About)
  const info = ref({})
//   const cnt = ref(-1)
  function getAbout() {
        info.value.name = about.value?.at(0).Name
        info.value.intro = about.value?.at(1).Intro
        info.value.interest = about.value?.at(2)["Interest&passion"]
        console.log(info)
        console.log("Hello")
  }
  onMounted(() => {
        store.dispatch('fetchAbout')
        getAbout()
  })
  </script>
  <style scoped>
    .row-1 {
        display: flex;
        justify-content: space-between;
    }
    .lead {
        display: flex;
        flex-direction: column;
        text-align: justify;
        font-size: 18px;
    }
    .fname {
        margin-bottom: 3%;
    }
    .intro{
        margin-bottom: 3%;
    }
    @media screen and (max-width: 400px){
        .row-1{
            margin-top: 100px;
            display: flex;
            flex-direction: column;
        }
    }
  </style>
  
  
  
  
  
  
  