<template>
  <nav class="navbar navbar-expand-lg sticky-top">
  <div class="container-fluid">
    <router-link class="navbar-brand" href="./LandingSection.vue">
        <img src="https://khanyapupuma.github.io/all-images/all-images/Images/gtlogo.png" alt="logo" class="img-fluid" loading="lazy">
    </router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link" aria-current="page" href="#home"><i class="bi bi-house-fill"></i> Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#about"><i class="bi bi-file-person"></i> About</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#resume"><i class="bi bi-person-vcard"></i> Education and Experience</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#project"><i class="bi bi-bookshelf"></i> Project</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#tools"><i class="bi bi-wrench-adjustable-circle-fill"></i> Tools</a>
        </li>
        <!-- <li class="nav-item">
          <a class="nav-link" href="#testimonials"><i class="bi bi-people-fill"></i> Testimonials</a>
        </li> -->
        <li class="nav-item">
          <a class="nav-link" href="#reachMe"><i class="bi bi-telephone"></i> Reach Me</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
</template>

<script>
export default {
   name: "NavBar"
  }

</script>


<style scoped>
li a:hover {
    background-color: #CBBDBD;
    ;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #CBBDBD;
}
nav{
  box-shadow: rgb(69, 68, 68) 2px 4px 2px;
  background-color: #000000;
}
</style>
