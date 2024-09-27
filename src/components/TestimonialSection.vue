<!-- <template>
  <div class="container">
    <div class="testimonialwrap">
      <div class="row align-items-center">
        <h1>Testimonials</h1>
        <div class="card-container" v-if="testimonials?.length">
          <Card v-for="value in testimonials" :key="value.id" class="card">
            <template #cardHeader>
              <img :src="value.profile" alt="" class="img" >
            </template>
            <template #cardBody>
              <div class="card-content">
                <h2>{{ value.name }}</h2>
                <p class="review-text">" {{ value.review }} "</p>
              </div>
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
  components: { Card },
  computed: {
    testimonials() {
      return this.$store.state.testimonials;
    }
  },
  mounted() {
    this.$store.dispatch('fetchTestimonials');
  }
}
</script>

<style scoped>
h1 {
  margin-bottom: 100px;
  text-shadow: 2px 2px 4px white;
  margin-top: 90px;
}

img {
  width: 200px;
  height: 290px;
  background-color: rgba(0, 0, 0, 0.8);
  border-radius: 10px;
}
img:hover{
  opacity: 0.9;
  transition: opacity 0.3s;
}

.card-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr); 
  gap: 20px;
  justify-items: center;
}

.card {
  position: relative;
  box-shadow: 4px 4px 6px rgba(0, 0, 0, 0.4);
  background-color: rgb(28, 27, 27);
  width: 270px;
  height: 350px;
  transition: opacity 0.3s ease-in-out;
}

.card-content {
  position: absolute;
  bottom: 0;
  padding: 20px;
  opacity: 0; 
  transition: opacity 0.3s ease-in-out;
}

.card:hover .card-content {
  opacity: 1; 
}

.card:hover {
  color: white;
  background-color: rgba(0, 0, 0, 0.8);
}

.review-text {
  color: white;
  font-style: italic;
}

</style> -->
