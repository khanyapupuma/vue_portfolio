<template>
  <footer class="container-fluid">
      <div class="row">
        <p class="lead">Khanya's portfolio &copy; 
          <span> {{cYear}}</span>
        </p>
      </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComp",
data(){
return{
    cYear: new Date().getUTCFullYear()

}
}

}
</script>

<style scoped>
footer{
  color: #CBBDBD ;
  background-color: black;
  font-family: 'Open Sans', Arial, sans-serif;
  font-weight: 700;
  font-style: italic;

}
</style>