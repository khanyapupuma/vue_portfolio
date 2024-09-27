<template>
  <div>
   
    <div class="container">
      <h1 class="resume">My Resume</h1>
      <div class="resumewrap">
        <div class="row align-items-center">
          <h2>Education</h2>
          <div class="card-container" v-if="education?.length">
            <Card v-for="value in education" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.imageURL" :alt="value.degree" width="240px">
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
    skills() {
      return this.$store.state.skills;
    }
  },
  mounted() {
    this.$store.dispatch('fetchEducation');
  }
}
</script>

<style scoped>


img {
  height: 200px;
}

.card-container {
  
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.card {
  box-shadow: 4px 4px 6px  rgba(0, 0, 0, 0.4);
  color: rgb(92, 78, 0);
  background-color: rgb(42, 42, 42);
  height: 250p;
  flex: 1 1 calc(33.333% - 20px);
  box-sizing: border-box;
  margin-bottom: 20px;
  max-width: calc(33.333% - 20px);
}

.gm{
  margin-top: 90px;
}

h1 {
  text-shadow: 2px 2px 4px rgb(19, 18, 18);
  margin-top: 90px;
}
h2{
  margin-top: 90px;
  margin-bottom: 50px;
}
.card:hover{
  border-width: 2px;
  border-color: rgb(191, 8, 191);
  transform: scale(1.05);
  box-shadow: 0 0 10px  rgba(0, 0, 0, 0.5);
  color:rgb(255, 217, 0) ;
}
</style>


  