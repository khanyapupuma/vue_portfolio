<template>
    <div class="container">
        <h1 class="about">About Me</h1>
        <div class="aboutwrap">
            <div class="row align-items-center">
                <div class="col-4">
                    <img src="https://khanyapupuma.github.io/all-images/all-images/Images/20240422_094850.jpg" alt="my image" loading="lazy" class="img-fluid">
                    <br>
                    <h2>
                        Khanya Pupuma
                    </h2>
                </div>
                <div class="col-8" about>
                    <div v-if="about?.length">
                  <p class="lead" v-for="(about, index) in about" :key="index">
                      {{ about }}.
                  </p>
                </div>
              <Spinner v-else/>
                </div>
            </div>
        </div>
    </div>
  </template>
  <script setup>
  import { computed, onMounted} from 'vue'
  import {useStore} from 'vuex'
  import Spinner from '@/components/Spinner.vue'
  const store = useStore()
  const about = computed(() => store.state.about)
  onMounted(() => {
      store.dispatch('fetchAbout')
  })
  </script>
  <style scoped>
    @media screen and (max-width: 400px){
        .row-1{
            margin-top: 100px;
            display: flex;
            flex-direction: column;
        }
    }
    .details{
        margin-right: 400px;
        margin-top: 60px;
        width: 580px;
    }
    .lead{
        width: 460px;
        height: 420px;
        margin-left: 150px;
    }
    .aboutwrap{
        margin-top: 150px;
    }
  </style>
  
  
  
  
  
  
  