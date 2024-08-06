<template>
    <div class="container">
       
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
                    <div v-if="about?.length" class=""> <h1 class="about">About Me</h1>
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
    .col-8{
        margin-bottom: 140px;
    }
    .lead{
        width: 500px;
        text-align: center;
        margin-left: 150px;
    }
    .aboutwrap{
        margin-top: 150px;
    }
    .about{
        margin-bottom: 150px;
        margin-right: 190px;
    }
    .img{
        width: 400px;
        height: 350px;
    }
    h1{
    text-shadow: 2px 2px 4px white;
    margin-top: 90px;
  }
  h2{
    text-shadow: 2px 2px 4px white;
  }
  img{
    border: solid 4px;
    width: 460px;
    height: 570px;
  } 
  .container{
    margin-left: 100px;
  }
  </style>