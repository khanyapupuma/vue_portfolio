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
              <p>{{ value.Info }}</p>
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
  color: rgb(0, 0, 0);
  text-shadow: 2px 2px 4px rgb(30, 28, 28);
  margin-bottom: 90px;
  padding-top: 10px;
}
img {
  height: 100px;
  border-radius: 4px;
}
/* p {
  color: rgb(92, 78, 0);
  margin-bottom: 40px;
} */
ul {
  color: rgb(210, 179, 0);
}
.softskill {
  margin-bottom: 250px;
  border-radius: 4px;
  background-color: rgb(42, 42, 42);
  width: 280px;
  justify-self: center;
  margin-left: 580px;
}
.card-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px; 
  justify-items: center;
}

.card {
  color: rgb(92, 78, 0);
  background-color: rgb(42, 42, 42);
  height: 440px; 
  width: 259px;
  box-sizing: border-box;
  padding: 20px;
}

h2 {
  margin-top: 20px;
  margin-bottom: 20px;
}

.card:hover {
  border-width: 2px;
  border-color: rgb(191, 8, 191);
  transform: scale(1.05);
  box-shadow: 0 0 10px  rgba(0, 0, 0, 0.5);
  color:rgb(255, 217, 0) ;

}
/* p:hover{
  color: rgb(255, 217, 0);
} */
</style>
