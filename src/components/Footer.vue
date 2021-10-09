<template>
  <footer>
    <div class="container">
      <div class="col col-right">
        <img src="@/assets/img/logo-white.svg" alt="Logo">

        <div class="social">
          <span class="icon icon-facebook"></span>
          <span class="icon icon-youtube"></span>
          <span class="icon icon-twitter"></span>
          <span class="icon icon-pinterest"></span>
          <span class="icon icon-instagram"></span>
        </div>
      </div>

      <div class="menu-footer">
        <div class="col">
          <a href="#">Home</a>
          <a href="#">Pricing</a>
          <a href="#">Products</a>
          <a href="#">About Us</a>
        </div>

        <div class="col">
          <a href="#">Careers</a>
          <a href="#">Community</a>
          <a href="#">Privacy policy</a>
        </div>
      </div>

      <div class="col col-right">
        <div class="form">
          <input type="text" placeholder="Updates in your inbox..."> 
          <Button :shadow="false">Go</Button>
        </div>
        <p class="copyright-desktop">Copyright 2020. All Rights Reserved</p>
      </div>
    </div>
    

    <p class="copyright-mobile">Copyright 2020. All Rights Reserved</p>
  </footer>
</template>


<script setup>
import Button from "./Button.vue";

</script>