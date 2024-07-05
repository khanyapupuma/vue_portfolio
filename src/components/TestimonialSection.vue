<template>
  <div class="container">
      <div class="testimonialwrap">
        <div class="row align-items-center">
          <h1>Testimonials</h1>
          <div class="col-4 row" v-if="testimonials?.length">
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
  border: solid;
}
</style>