<template>
  <div>
   
    <div class="container" id="project">
      <h1 class="resume">My Resume</h1>
      <div class="resumewrap">
        <div class="row align-items-center">
          <h2>Education</h2>
          <div class="card-container" v-if="education?.length">
            <Card v-for="value in education" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.imageURL" :alt="value.degree" width="300px">
              </template>
              <template #cardBody>
                <h2>{{ value.school }}</h2>
                <p>{{ value.degree }}</p>
                <p>{{ value.graduation_year }}</p>
                <p>{{ value.location }}</p>
              </template>
            </Card>
          </div>
          <div v-else class="d-flex">
            <div class="spinner-border" role="status">
            </div>
          </div>
        </div>
      </div>
    </div>

  
    <div class="container">
      <div class="resumewrap">
        <div class="row align-items-center">
          <h2>My Projects</h2>
          <div class="card-container" v-if="projects?.length">
            <Card v-for="value in projects" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.image" alt="" width="300px">
              </template>
              <template #cardBody>
                <h2>{{ value.projectName }}</h2>
                <p>{{ value.description }}</p>
                <a :href="value.vercel"><button>Vercel</button></a><br>
                <a :href="value.github"><button><i class="bi bi-github"></i> Github</button></a>
              </template>
            </Card>
          </div>
        </div>
      </div>
    </div>

    <div class="container">
      <div class="resumewrap">
        <div class="row align-items-center">
          <h2>My Skills</h2>
          <div class="card-container" v-if="skills?.length">
            <Card v-for="value in skills" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.image" alt="" width="300px">
              </template>
              <template #cardBody>
                <h2>{{ value.title }}</h2>
              </template>
            </Card>
          </div>
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
    education() {
      return this.$store.state.education;
    },
    projects() {
      return this.$store.state.projects;
    },
    skills() {
      return this.$store.state.skills;
    }
  },
  mounted() {
    this.$store.dispatch('fetchEducation');
    this.$store.dispatch('fetchProjects');
    this.$store.dispatch('fetchSkills');
  }
}
</script>

<style scoped>


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


  