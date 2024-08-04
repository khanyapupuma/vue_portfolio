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
          <div class="form-group">
            <input type="text" placeholder="Your email" class="d" id="emailInput" v-model="form.email"> <br>
          </div>
          <div class="form-group">
            <input type="text" placeholder="Phone number" class="d" id="phone" v-model="form.phone"> <br>
          </div>
          <div class="form-group">
            <textarea name="" id="" rows="10" cols="40" class="d1" placeholder="Message to Us" v-model="form.message"></textarea>
          </div>
          <br>
          <div class="button-group">
            <button type="button" class="but" @click="clearForm">Clear</button>
            <button type="submit" class="but" @click="handleSubmit">Send Message</button>
          </div>
          <p v-if="error" class="error-message">{{ error }}</p>
        </div>
      </div>
      <div class="img">
        <img src="https://khanyapupuma.github.io/all-images/all-images/Images/file.png" alt="" height="390px">
        <h1>THANKS FOR VISITING!</h1>
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

.but {
  margin-left: 50px;
  color: red;
  background-color: #000000;
  border-radius: 3px;
  margin-bottom: 5px;
}

.nov {
  margin-left: 25px;
  margin-top: 50px;
  text-align: center;
  width: 500px;
  padding: 80px;
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
  height: 80px;
  margin-top: 10px;
  margin-left: 40px;
  margin-bottom: 10px;
  box-sizing: border-box;
  vertical-align: top;
}

h1 {
  text-shadow: 2px 2px 4px white;
  margin-top: 90px;
  text-align: center;
  color: white;
  font-weight: bold;
}

.error-message {
  color: #FF8C00;
  font-weight: bold;
  margin-top: 0.5rem;
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