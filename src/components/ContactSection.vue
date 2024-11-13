<template>
    <div class="rim">
      <div class="dim">
        <main class="hm"><h1>Contact Me</h1></main>
      </div>
      <div class="nov">
        <div class="ron">
          <div class="form-group">
            <input type="text" placeholder="Your name & surname" class="d" id="nameInput" v-model="form.name"> <br>
          </div>
          <div class="form-group ">
            <input type="text" placeholder="Your email" class="d" id="emailInput" v-model="form.email"> <br>
          </div>
          <div class="form-group">
            <textarea name="" id="" rows="10" cols="40" class="d1" placeholder="Message to Us" v-model="form.message"></textarea>
          </div>
          <br>
          <div class="button-group">
            <button type="button" class="but but2" @click="clearForm">Clear</button>
            <button type="submit" class="but but1" @click="handleSubmit">Send Message</button>
          </div>
          <p v-if="error" class="error-message">{{ error }}</p>
        </div>
        <div class="links">
          <h2>Direct Contact Me</h2>
          <br>
          <p class="p">
            <a href="https://www.linkedin.com/in/khanya-pupuma-41a171324/" target="_blank"><i class="bi bi-linkedin"></i> </a>My LinkedIn
            <br>
            <a href="mailto:khalilpupuma@gmail.com" target="_blank"><i class="bi bi-envelope-at-fill"></i></a> khalilpupuma@gmail.com
            <br>
            <a href="tel:+27733926856" target="_blank"><i class="bi bi-telephone-fill"></i></a> +27 73 392 6856 or  +27 63 646 9674
            <br>
            <a href="https://www.google.com/maps/place/Philippi,+Cape+Town/@-34.0353778,18.576035,13z/data=!3m1!4b1!4m6!3m5!1s0x1dcc45d16205a045:0x422d16fa23c5b3cb!8m2!3d-34.0187678!4d18.5634409!16s%2Fm%2F05h4xnc?entry=ttu&g_ep=EgoyMDI0MTAwMS4wIKXMDSoASAFQAw%3D%3D" target="_blank"><i class="bi bi-geo-alt-fill"></i></a> Philippi, Cape Town
          </p>
        </div>
      </div>
    </div>
  </template>

<style scoped>
.img {
  background-image: url("https://khanyapupuma.github.io/all-images/all-images/Images/blk2.webp");
  background-repeat: no-repeat;
  background-size: 100% 100%;
  padding: 30px;
}
.p{
  text-align: left;
  color: white;
}

.but {
  margin-left: 110px;
  color: rgb(255, 255, 255);
  background-color: #000000;
  border-radius: 3px;
  margin-bottom: 5px;
}
h2{
  color: white;
}

.nov {
  display: flex;
  justify-content: space-between; 
  align-items: flex-start; 
  margin-left: 25px;
  margin-top: 50px;
  text-align: center;
  width: 100%;
  padding: 80px;
}

.ron {
  margin-right: 20px;
  background-color: rgb(42, 42, 42);
  width: 60%; 
  height: auto;
  align-content: center;
  border-radius: 20px;
  padding: 20px;
}

.d {
  width: 600px;
  height: 50px;
  border-radius: 5px;
  margin-left: 40px;
  margin-top: 10px;
  margin-bottom: 10px;
}

.d1 {
  border-radius: 5px;
  width: 600px;
  height: 180px;
  margin-top: 10px;
  margin-left: 40px;
  margin-bottom: 10px;
  box-sizing: border-box;
  vertical-align: top;
}
.links {
  background-color: rgb(52, 52, 52); 
  width: 28%; 
  height: auto;
  padding: 20px;
  border-radius: 20px;
}

.links a {
  margin: 15px;
  text-decoration: none;
  color: #337ab7;
  transition: color 0.2s ease-in-out;
}

.links p {
  justify-content: left;
  margin-bottom: 10px;
}

.links a {
  text-decoration: none; 
  color: #337ab7; 
  transition: color 0.2s ease-in-out; 
}

.links a:hover {
  color: #23527c; 
}

.links i {
  margin-right: 5px; 
}
h1 {
  text-shadow: 2px 2px 4px rgb(30, 28, 28);
  margin-top: 90px;
  text-align: center;
  color: rgb(0, 0, 0);
  font-weight: bold;
}

.error-message {
  color: #FF8C00;
  font-weight: bold;
  margin-top: 0.5rem;
}
.but1:hover{
  color: #3ab312;
  transform: scale(1.1);
}
.but2:hover{
  color: red;
  transform: scale(1.1);
}

button {
  padding: 0.5rem 1rem;
  font-size: 1rem;
  margin-left: 1rem;
  cursor: pointer;
  border: none;
  border-radius: 4px;
}

.button-group {
  display: flex;
  /* justify-content: flex-end; */
  /* align-items: center; */
}

@media (max-width: 768px) {
  .nov {
    width: 100%;
    margin-left: 0;
  }

  .d,
  .d1 {
    width: calc(100% - 80px);
    margin-left: 40px;
  }

  .button-group {
    justify-content: center;
  }
}
</style>
  <script>
  import Swal from 'sweetalert2';
  import emailjs from 'emailjs-com';
  
  export default {
    data() {
      return {
        form: {
          name: '',
          email: '',
          phone: '',
          message: ''
        },
        error: '',
        loading: false 
      };
    },
    methods: {
      handleSubmit() {
        this.error = '';
        if (!this.form.name || !this.form.email || !this.form.phone || !this.form.message) {
          this.error = "Please complete all fields before submitting.";
          return;
        }
        this.loading = true; 
        const serviceID = 'service_ajp7c9c';
        const templateID = 'template_ezevsqn';
        const userID = 'nr84-uEp_HOD_rvlC';
        emailjs.send(serviceID, templateID, this.form, userID)
          .then(() => {
            Swal.fire({
              icon: 'success',
              title: 'Message Sent',
              text: 'Thank you for getting in touch! I will be sure to reply at my earliest convenience.',
            });
            this.clearForm();
          })
          .catch(() => {
            Swal.fire({
              icon: 'error',
              title: 'Error',
              text: 'There was an error sending your message. Please try again later.',
            });
          })
          .finally(() => {
            this.loading = false; 
          });
      },
      clearForm() {
        this.form = {
          name: '',
          email: '',
          phone: '',
          message: ''
        };
        this.error = '';
      }
    }
  };
  </script>