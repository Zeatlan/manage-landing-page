<template>
  <div class="bg"></div>
  <div class="bg bg2"></div>
  <Header />

  <!-- Home Section -->
  <section id="home">
    <div class="container">
      <div class="intro">
        <h1>Bring everyone together to build better products.</h1>

        <p>Manage makes it simple for software teams to plan day-to-day tasks while keeping the larger team goals in view.</p>

        <Button>Get Started</Button>
      </div>
      
      <div class="images">
        <img src="@/assets/img/illustration-intro.svg" alt="Illustration intro">
      </div>
    </div>
  </section>
  <!-- End Home Section -->

  <!-- Manage Section -->
  <section id="manage">
    <div class="container">
      <div class="intro">
        <h2>What's different about Manage?</h2>

        <p>Manage provides all the functionality your team needs, without the complexity. Our software is tailor-made for modern digital product teams.</p>
      </div>
      
      <div class="features">
        <div class="feature" v-for="(feature, idx) in features" :key="idx">
          <Feature :num="idx+1" :title="feature.title">
            {{ feature.body }}
          </Feature>
        </div>
      </div>
    </div>
  </section>
  <!-- End Manage Section-->

  <!-- Client Section -->
  <section id="client">
    <h2>What they've said</h2>

    <swiper
    :slides-per-view="slidesPerView"
    :space-between="50"
    :autoplay="true"
    :pagination="pagination"
    class="clients">
      <swiper-slide class="card" v-for="(client, idx) in clients" :key="idx">
        <Client :avatar="client.avatar" :name="client.name">
          {{ client.opinion }}
        </Client>
      </swiper-slide>
    </swiper>
    
    <div class="get-started">
      <Button >Get Started</Button>
    </div>
  </section>
  <!-- End Client Section -->

  <!-- Brand Section -->
  <section id="brand">
    <div class="container">
      <h2>Simplify how your team works today.</h2>

      <Button :reverse="true" :shadow="false">Get Started</Button>
    </div>
  </section>
  <!-- End Brand Section -->

  <!-- Footer -->
  <Footer />
  <!-- End Footer-->
</template>

<script setup>
import Button from '@/components/Button';
import Client from '@/components/Client';
import Feature from '@/components/Feature';
import Footer from '@/components/Footer';
import Header from '@/components/Header';
import { defineComponent, ref } from "@vue/runtime-core";
// Import Swiper core and pagination modules
import SwiperCore, {
Pagination
} from 'swiper';
// Import Swiper scss
import "swiper/components/pagination/pagination.min.css";
import "swiper/swiper.scss";
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';


const features = ref([
  {
    'title': `Track Company-wide progress`,
    'body': `See how your day-to-day tasks fit into the wider vision.
          Go from tracking progress at the milestone level all the way done to the smallest of details. Never lose sight of
          the bigger picture again.`
  },
  {
    'title': `Avanced built-in reports`,
    'body': `Set internal delivery estimates and track progress toward
          company goals. Our customisable dashboard helps you
          build out the reports you need to keep key stakeholders
          informed.`
  },
  {
    'title': `Everything you need in one place`,
    'body': `Stop jumping from one service to another to
          communicate, store files, track tasks and share
          documents. Manage offers an all-in-one team
          productivity solution.`
  }
]);

const clients = ref([
  {
    'avatar': `avatar-anisha`,
    'name': `Anisha Li`,
    'opinion': `Manage has supercharged our team's workflow. The
    ability to maintain visibility on larger milestones at all times
    keeps everyone motivated.`
  },
  {
    'avatar': `avatar-ali`,
    'name': `Ali Bravo`,
    'opinion': `We have been able to cancel so many other subscriptions since using Manage. 
    There is no more cross-channel confusion and everyone is much more focused. `
  },
  {
    'avatar': `avatar-richard`,
    'name': `Richard Watts`,
    'opinion': `Manage allows us to provide structures and process. it
    keeps us organized and focused. I can't stop recommending
    them to everyone I talk to! `
  },
  {
    'avatar': `avatar-shanai`,
    'name': `Shanai Gough`,
    'opinion': `Their software allows ur to track, manage and collaborate
    on our projects from anywhere. It keeps the whole team in-sync
    without being intrusive. `
  },
])

const slidesPerView = ref(3);
const pagination = ref(false);

// Mobile device
if(window.screen.width <= 480) {
  slidesPerView.value = 1;
  pagination.value = true;
}

defineComponent({
  Header,
  Button,
  Feature,
  Client,
  Footer,
  Swiper,
  SwiperSlide
})

SwiperCore.use([Pagination]);
</script>
