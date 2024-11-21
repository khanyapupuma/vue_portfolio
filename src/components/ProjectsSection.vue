<template>
  <div class="container">
    <div class="resumewrap">
      <div class="row align-items-center">
        <h1 class="prot">My Projects</h1>
        <div class="card-container" v-if="projects?.length">
          <Card v-for="value in projects" :key="value.id" class="card">
            <template #cardHeader>
              
              <img :src="value.image" alt="" class="img">
              <h5 class="gm">{{ value.projectName }}</h5>
              <!-- <p>{{ value.description }}</p> -->
            </template>
            <template #cardBody>
              <div class="buttons">
                <a :href="value.vercel" target="_blank"><button><i class="bi bi-view-stacked"></i> Demo</button></a>
                <a :href="value.github" target="_blank"><button><i class="bi bi-github"></i> Github</button></a>
              </div>
            </template>
          </Card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from '@/components/Card.vue';

export default {
  components: {
    Card
  },
  computed: {
    projects() {
      return this.$store.state.projects;
    }
  },
  mounted() {
    this.$store.dispatch('fetchProjects');
  }
}
</script>

<style scoped>
h1 {
    padding-top: 150px;
  margin-bottom: 100px;
  text-shadow: 2px 2px 4px rgb(30, 28, 28);
  /* margin-top: 90px; */
  text-align: center;
  color: rgb(0, 0, 0);
  font-weight: bold;
}

img {
  border-radius: 2px;
  height: 220px; 
  width: fit-content;
  opacity: 1; /* Default opacity */
  transition: opacity 0.2s ease, transform 0.2s ease;
}
/* img:hover{
  opacity: 0.3; 
} */

.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.card {
  color: rgb(190, 189, 185);
  background-color: rgb(42, 42, 42);
  height: 370px; 
  flex: 1 1 calc(35% - 20px); /* Updated to 50% for two cards per row */
  box-sizing: border-box;
  margin-bottom: 20px;
  max-width: calc(35% - 20px); /* Updated to 50% for two cards per row */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 15px;
  transition: transform 0.2s ease; /* Smooth transition for opacity and transform */
}


.gm {
  margin-top: 10px;
  margin-bottom: 10px;
  text-align: center;
}

/* p {
  text-align: center;
  color: rgb(210, 179, 0);
  margin-bottom: 15px;
} */

.buttons {
  display: flex;
  justify-content: center;
}

button {
  width: 90px;
  background-color: #dbd7b9;
  color: black;
  font-weight: bold;
  border-radius: 4px;
  margin: 5px;
}

a button:hover {
  background-color: #000000;
  color: rgb(255, 248, 248);
}

.card:hover {
  
  border-width: 2px;
  border-color: rgb(191, 8, 191);
  transform: scale(1.05);
  /* box-shadow: 0 0 10px rgba(0, 0, 0, 0.5); */
  color: rgb(255, 217, 0);
}
.img{
  filter: grayscale(100%);
}
.img:hover{
  filter: grayscale(0%);
}

@media (max-width: 768px) {
  .card-container {
    flex-direction: column;
  }

  .card {
    width: 100%;
    max-width: 100%;
  }

  .img{
    width: 300px;
  }
}

</style>
