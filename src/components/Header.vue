<template>
<div id="page-mask"></div>
  <header>
    <nav class="navbar">
      <div class="container">
          <img src="@/assets/img/logo.svg" alt="Logo">

        <!-- Desktop Menu-->
        <div class="menu">
          <ul>
            <li><a href="#">Pricing</a></li>
            <li><a href="#">Product</a></li>
            <li><a href="#">About Us</a></li>
            <li><a href="#">Carrers</a></li>
            <li><a href="#">Community</a></li>
          </ul>

          <Button :hoverable="true">Get Started</Button>
        </div>
        
        <!-- Responsive Hamburger Menu -->
        <div @click="openMenu" class="menu-hamburger">

          <div class="menu-btn">
            <div class="menu-btn__burger"></div>
          </div>
          
        </div>
        <!-- End responsive Hamburger Menu -->

        <ul class="menu-mobile">
          <li><a href="#">Pricing</a></li>
          <li><a href="#">Product</a></li>
          <li><a href="#">About Us</a></li>
          <li><a href="#">Carrers</a></li>
          <li><a href="#">Community</a></li>
        </ul>
      
      </div>
    </nav>
  </header>
</template>

<script setup>

import Button from '@/components/Button';
import { defineComponent, ref } from "@vue/runtime-core";

const displayed = ref(false);

defineComponent({
  Button
});

document.addEventListener('click', function(event) {
  if(displayed.value === true){
    const mobileMenu = document.querySelector('ul.menu-mobile');
    const menuBtn = document.querySelector('.menu-btn');
    const isClickInsideElement = mobileMenu.contains(event.target);
    const isClickInsideElementTwo = menuBtn.contains(event.target);
    if (!isClickInsideElement && !isClickInsideElementTwo) 
      openMenu();
  }
});

function openMenu() {
  const mobileMenu = document.querySelector('ul.menu-mobile');
  const mask = document.querySelector('#page-mask');
  const menuBtn = document.querySelector('.menu-btn');

  if(displayed.value){ 
    mobileMenu.style.display = "none";
    mask.style.display = "none";
    menuBtn.classList.remove('open');
    displayed.value = false;
  }
  else{ 
    mobileMenu.style.display = "block";
    mask.style.display = "block";
    menuBtn.classList.add('open');
    displayed.value = true;
  }
}
</script>