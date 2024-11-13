<template>
  <div class="container">
    <div class="resumewrap">
      <div class="row align-items-center">
        <h1>My Skills</h1>
        <div class="card-container" v-if="skills?.length">
          <Card v-for="value in skills" :key="value.id" class="card">
            <template #cardHeader>
              <img :src="value.image" alt="" width="130px" />
            </template>
            <template #cardBody>
              <h2>{{ value.title }}</h2>
              <p>{{ value.Proficiency }}</p>
              <h5>{{ value.Info }}</h5>
            </template>
          </Card>
        </div>
       
      </div>
      <h1>Soft Skills</h1>
      <div class="card-container">
          <Card class="c2">
                <template #cardHeader>
                  <!-- <img  src="https://img.icons8.com/external-smashingstocks-flat-smashing-stocks/66/external-Public-Speaking-government-smashingstocks-flat-smashing-stocks.png" /> -->
                <!-- </template>
                <template #cardBody>  -->
                    <h3>Soft Skills</h3>
                    <br>
                    <h6>Public Speaking</h6>
                    <h6>Analytical Thinking</h6>
                    <h6>Teamwork</h6>
                    <h6>Time Management</h6>
                    <h6>Scrum</h6>
                    <h6>English Proficiency</h6>
                    <h6>Search Engine Optimization</h6>
                    <h6>Communication</h6>
                    
                </template>
           
              </Card>
              
        </div>
    </div>
  </div>
</template>

<script>
import Card from '@/components/Card.vue';

export default {
  components: {
    Card,
  },
  computed: {
    skills() {
      return this.$store.state.skills;
    },
  },
  mounted() {
    this.$store.dispatch('fetchSkills');
  },
};
</script>

<style scoped>
h1 {

  margin-bottom: 100px;
  text-shadow: 2px 2px 4px rgb(30, 28, 28);
  margin-top: 90px;
  text-align: center;
  color: rgb(0, 0, 0);
  font-weight: bold;
}
img {
  height: 100px;
  border-radius: 4px;
}
.c2{
  height: 400px;
}

h6{
  margin: 12px;
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.card {
  color: rgb(190, 189, 185);
  background-color: rgb(42, 42, 42);
  height: 380px; 
  width: 370px;
  box-sizing: border-box;
  margin-bottom: 20px;
  max-width: calc(35% - 20px); /* Updated to 50% for two cards per row */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 15px;
  transition: transform 0.2s ease;
}

h2 {
  margin-top: 20px;
  margin-bottom: 20px;
}
h2:hover{
  color:rgb(255, 217, 0) ;
}

.card:hover {
  border-width: 2px;
  border-color: rgb(191, 8, 191);
  transform: scale(1.05);
  box-shadow: 0 0 10px  rgba(0, 0, 0, 0.5);
  

}
/* p:hover{
  color: rgb(255, 217, 0);
} */
</style>
