<template>
    <div class="container">
      <div class="row vh-100 align-items-center">
          <div class="col">
                <div class="col">
              <div id="details">
                  <h1 class="display-1">Welcome<br>I AM <br> Khanya Pupuma</h1>
                  <h3 v-if="title"><span>{{ title }}</span>
                  </h3>
                  <Spinner v-else/>
              </div>
          </div>
      </div>
          </div>
         
    </div>
  </template>
  <script setup>
  import { computed, onMounted, ref } from 'vue'
  import {useStore} from 'vuex'
  import Spinner from '@/components/Spinner.vue'
  const store = useStore()
  const jobTitle = computed(() => store.state.jobTitle)
  const title = ref('a software developer')
  const cnt = ref(-1)
  function repeat(){
      try{
          if (cnt.value == jobTitle.value?.length) cnt.value = 0
          title.value = jobTitle.value?.at(cnt.value)?.title;
          setTimeout(repeat, 2000)
          cnt.value ++
      }catch (e) {
          //
      }
  }
  onMounted(() => {
      store.dispatch('fetchJobTitle')
      repeat()
  })
  </script>
  <style scoped>
  .container{
    background-image: url('https://khanyapupuma.github.io/all-images/all-images/Images/blk3.webp');
    background-repeat: no-repeat; 
    background-size:100% 100%;
  }
  h1{
    text-shadow: 2px 2px 4px white;
  }
  span{
    text-shadow: 2px 2px 4px pink;
  }
  </style>