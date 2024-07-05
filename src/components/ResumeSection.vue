<template>
  
  <div class="container">
        <h1 class="resume">My Resume</h1>
        <div class="resumewrap">
            <div class="row align-items-center">
              <h2>Education</h2>
                <div class="col-8"  v-if="education?.length">
                    <Card v-for="value in education" :key="value.id">
                      <template #cardHeader>
                      <img :src="value.imageURL" :alt="value.degree">
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
          <div class="col-4 row" v-if="projects?.length">
            <Card v-for="value in projects" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.image" alt="" width="360px">
              </template>
              <template  #cardBody>
                 <h2>{{ value.projectName }}</h2>
                 <p>{{ value.description }}</p>
                 <a :href=value.vercel><button>Vercel</button></a><br>
                 <a :href=value.github><button>Github</button></a>
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
          <div class="col-4 row" v-if="skills?.length">
            <Card v-for="value in skills" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.image" alt="" width="360px">
              </template>
              <template  #cardBody>
                 <h2>{{ value.title }}</h2>
              </template>
            </Card>
          </div>
        </div>
      </div>
    </div> 
  </template> 
  
  <script>
  import Card from '@/components/Card.vue'
;
  export default {
    components: {
      Card
    },
    computed: {
      education(){
        return this.$store.state.education
      },
      projects(){
        return this.$store.state.projects
      },
      skills(){
        return this.$store.state.skills
      }
    },
    mounted(){
      this.$store.dispatch('fetchEducation')
       this.$store.dispatch('fetchProjects')
       this.$store.dispatch('fetchSkills')
    }
     
    
  }
  </script>
  
  <style scoped>
  img{
    height: 300px;
  }
.col-8{
  width: 450px;
}
.card{
  border: solid;
}
  </style>

  