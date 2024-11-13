<template>
  <div>
   
    <div class="container">
      <div class="resumewrap">
        <div class="row align-items-center">
          <h1>Education</h1>
          <div class="card-container" v-if="education?.length">
            <Card v-for="value in education" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.imageURL" :alt="value.degree" width="240px">
              </template>
              <template #cardBody>
                <h3>{{ value.school }}</h3>
                <!-- <p>{{ value.degree }}</p> -->
                <p>{{ value.graduation_year }}</p>
                <!-- <p>{{ value.location }}</p> -->
              </template>
            </Card>
          </div>
          <div v-else class="d-flex">
            <div class="spinner-border" role="status">
            </div>
          </div>
        </div>
        <h1>Experience</h1>
            <div class="card-container">
              <Card>
                <template #cardHeader>
                  <img src="data:image/jpeg;base64,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" alt="">
                </template>
                <template #cardBody> 
                    <h3>Life Choices Studio</h3>
                    <p>Sept 2024 - present</p>
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
  color: rgb(190, 189, 185);
  background-color: rgb(42, 42, 42);
  height: 250p;
  flex: 1 1 calc(33.333% - 20px);
  box-sizing: border-box;
  margin-bottom: 20px;
  max-width: calc(33.333% - 20px);
  transition: transform 0.2s ease;
}

.gm{
  margin-top: 90px;
}

h1 {
  padding-top: 100px;
  margin-bottom: 50px;
  text-shadow: 2px 2px 4px rgb(30, 28, 28);
  /* margin-top: 90px; */
  text-align: center;
  color: rgb(0, 0, 0);
  font-weight: bold;
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


  