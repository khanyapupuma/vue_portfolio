<template>
  <div class="container">
      <div class="testimonialwrap">
        <div class="row align-items-center">
          <h1>Testimonials</h1>
          <div class="card-container" v-if="testimonials?.length">
            <Card v-for="value in testimonials" :key="value.id" class="card">
              <template #cardHeader>
                <img :src="value.profile" alt="" width="360px">
              </template>
              <template  #cardBody>
                 <h2>{{ value.name }}</h2>
                 <p>{{ value.review }}</p>
              </template>
            </Card>
          </div>
        </div>
      </div>
    </div> 
</template>

<script>
import Card from '@/components/Card.vue'

export default {
  components:{Card},
  computed: {
      testimonials(){
        return this.$store.state.testimonials
      }},
      mounted(){
        this.$store.dispatch('fetchTestimonials')}
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
h1{
    text-shadow: 2px 2px 4px white;
    margin-top: 90px;
  }
  
.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px; 
  justify-content: center; 
}
.card:hover{
  border-color: rgb(195, 10, 195);
}


</style>