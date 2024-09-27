<template>
  <div class="container">
    <div class="resumewrap">
      <div class="row align-items-center">
        <h1 class="prot">My Projects</h1>
        <div class="card-container" v-if="projects?.length">
          <Card v-for="value in projects" :key="value.id" class="card">
            <template #cardHeader>
              <h2 class="gm">{{ value.projectName }}</h2>
              <img :src="value.image" alt="" class="img">
              <p>{{ value.description }}</p>
            </template>
            <template #cardBody>
              <div class="buttons">
                <a :href="value.vercel"><button><i class="bi bi-view-stacked"></i> Demo</button></a>
                <a :href="value.github"><button><i class="bi bi-github"></i> Github</button></a>
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
  margin-bottom: 100px;
}

img {
  border-radius: 2px;
  height: 120px; 
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.card {
  color: rgb(92, 78, 0);
  background-color: rgb(42, 42, 42);
  height: 450px; 
  flex: 1 1 calc(33.333% - 20px);
  box-sizing: border-box;
  margin-bottom: 20px;
  max-width: calc(33.333% - 20px);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 15px;
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
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  color: rgb(255, 217, 0);
}
</style>
