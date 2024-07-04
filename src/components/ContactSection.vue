<template>
    <div class="rim">
 <div class="dim"> 
        <main class="hm"><h1>Contact Me</h1></main>
            </div>
     <div class="nov">
        <h5 class="dc">Contact Us:+27 73 392 6856 <br>
            Email Me:khalilpupuma@gmail.com</h5>
        <h3>Enter:</h3>
        <div class="ron">
<input type="text" placeholder="Your name & surname" class="d" id="nameInput"> <br>
<input type="text" placeholder="Your email" class="d" id="emailInput"> <br>
<input type="text" placeholder="Phone number" class="d" id="phone"> <br>
<textarea name="" id="" rows="10" cols="40" class="d1"  placeholder="Message to Us"></textarea>
</div>
<br>
 <button type="submit" class="but" id="submitButton">Send Message</button>
     </div>
     <div class="img"><img src="https://khanyapupuma.github.io/all-images/all-images/Images/file.png" alt=""></div>
     </div>
</template>

<script>
export default {

}
</script>

<style scoped>
 .rim{
        background-image: url("https://khanyapupuma.github.io/all-images/all-images/Images/blk2.webp");
        background-repeat: no-repeat; 
        background-size:100% 100%;
    }                 
.but{margin-left: 50px;
    color: red;
     background-color: #000000;
     border-radius: 3px;
     margin-bottom: 5px;
}
.nov{
    
    background-color: rgba(0, 0, 0, 0.8);
   margin-left: 25px;
   margin-top: 50px;
   text-align: center;
  border: solid;
  width: 500px;
}                
.d{
    width: 395px;
    height: 40px;
    border-radius: 5px;
    margin-left: 40px;
    margin-top: 10px;
    margin-bottom: 10px;
}

.d1{ border-radius: 5px;
    width: 400px;
    height: 300px;
    align-content: start;
    margin-top: 10px;
    margin-left: 35px;
    margin-bottom: 10px;
    box-sizing: border-box;
    vertical-align: top;
    
}
</style>