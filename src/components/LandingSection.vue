<template>
  <div class="container">
    <div class="row vh-100 align-items-center">
      <div class="col">
        <div class="d-flex align-items-center">
          <!-- Title Section -->
          <div id="details" class="col-md-6">
            <h1 class="display-1">Welcome<br />I AM <br />Khanya Pupuma</h1>
            <h3 v-if="title"><span>{{ title }}</span></h3>
            <Spinner v-else />
          </div>
          
          <!-- Image Section -->
          <div class="col-md-6">
            <img
              src="https://khanyapupuma.github.io/all-images/all-images/Images/20240422_094850.jpg"
              alt="my image"
              loading="lazy"
              class="img-fluid img"
              width="390px"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed, onMounted, ref } from 'vue';
import { useStore } from 'vuex';
import Spinner from '@/components/Spinner.vue';

const store = useStore();
const jobTitle = computed(() => store.state.jobTitle);
const title = ref('a software developer');
const cnt = ref(-1);

function repeat() {
  try {
    if (cnt.value == jobTitle.value?.length) cnt.value = 0;
    title.value = jobTitle.value?.at(cnt.value)?.title;
    setTimeout(repeat, 2000);
    cnt.value++;
  } catch (e) {
    //
  }
}

onMounted(() => {
  store.dispatch('fetchJobTitle');
  repeat();
});
</script>

<style scoped>
.container {
  background-image: url('data:image/jpeg;base64,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');
  background-size: cover;
}

#details {
  color: rgb(249, 249, 249);
  text-shadow: 4px 4px  8px rgba(0, 0, 0, 0.944);

}

h1,
h2 {
  font-weight: bold;
  color: white;
  text-shadow: 2px 2px  4px rgba(0, 0, 0, 0.944);
}

.img {
  max-width: 100%;
  height: auto;
  border-radius: 90%;
  border: solid 3px rgba(0, 0, 0, 0.411);
}

/* Mobile responsive */

/* Base styles remain the same */
h1 {
  text-shadow: 2px 2px 4px rgb(30, 28, 28);
  color: rgb(0, 0, 0);
  font-weight: bold;
  text-align: center;
}

.aboutwrap {
  margin-top: 100px;
  text-align: center;
}

p {
  width: 90%; /* Full width for better responsiveness */
  margin: 0 auto 15px; /* Center and space out the paragraphs */
  text-align: center;
  display: block; /* Ensures paragraphs are properly centered */
}

/* Tablet devices (max-width: 768px) */
@media screen and (max-width: 768px) {
  .container {
    margin-left: 15px;
    margin-right: 15px;
  }

  p {
    font-size: 14px; /* Smaller font size for readability */
  }

  h1 {
    font-size: 26px; /* Adjust heading size */
  }

  .aboutwrap {
    margin-top: 50px; /* Reduce top margin */
  }
}

/* Mobile devices (max-width: 480px) */
@media screen and (max-width: 480px) {
  .container {
    margin: 0 10px; /* Minimal margins for small screens */
  }

  h1 {
    font-size: 22px; /* Further reduce heading size */
  }

  p {
    font-size: 12px; /* Smaller text size for readability */
    margin-bottom: 10px; /* Reduce space between paragraphs */
  }

  .aboutwrap {
    margin-top: 30px; /* Reduce top margin further */
  }

  .img {
    width: 100%; /* Adjust images to fit within the container */
    height: auto; /* Maintain aspect ratio */
  }
}

</style>
