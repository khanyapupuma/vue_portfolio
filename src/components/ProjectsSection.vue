<template>
<div class="container">
      <div class="resumewrap">
        <div class="row align-items-center">
          <h1 class="prot">My Projects</h1>
          <div class="card-container" v-if="projects?.length">
            <Card v-for="value in projects" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.image" alt="" width="300px">
              <!-- </template>
              <template #cardBody> -->
                <h2 class="gm">{{ value.projectName }}</h2>
                <p>{{ value.description }}</p>
                <a :href="value.vercel"><button>Vercel</button></a>
                <a :href="value.github"><button><i class="bi bi-github"></i> Github</button></a>
              </template>
            </Card>
          </div>
        </div>
      </div>
    </div>
</template>
<script>
import  Card from '@/components/Card.vue';


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

h1{
    margin-bottom: 100px;
}
img {
  height: 300px;
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.card {
  color: white;
  background-color: transparent;
  height: 150p;
  border: solid 7px;
  border-top-color: rgb(6, 6, 110);
  border-left-color: rgb(6, 6, 100);
  border-bottom-color: rgb(112, 0, 0);
  border-right-color: rgb(152, 17, 17);
  flex: 1 1 calc(33.333% - 20px);
  box-sizing: border-box;
  margin-bottom: 20px;
  max-width: calc(33.333% - 20px);
}

.gm{
  margin-top: 90px;
}

h1 {
  text-shadow: 2px 2px 4px white;
  margin-top: 90px;
}
h2{
  margin-top: 90px;
  margin-bottom: 50px;
}
button{
  width: 90px;
  color: black;
  font-weight: bold;
  border-radius: 4px;
  margin: 5px;
}
a button:hover {
    background-color: #000000;
    ;
    color: rgb(255, 248, 248);
}
.card:hover{
  border-color: rgb(191, 8, 191);
}
</style>