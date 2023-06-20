<template>
    <div>
      <a href="">
      <transition-group name="fade" tag="div" >
        <div v-for="i in [currentIndex]" :key="i" class="services">
        <div class="ServicesLogo rounded-circle">
          <img src="../../assets/logo.png" alt="logo">
        </div>
        <a href="#" id="servicesH1">
            <font size="+10" id="ServicesH1"><strong>Services</strong></font>
          </a>
          <img :src="currentImg" />
        </div>
    </transition-group>
      </a>
    </div>
  </template>
  
  <script>
  export default {
    name: "servicesComponent",
    data() {
      return {
        images: [
        require("../../assets/service_car/image1.png"),
        require("../../assets/service_car/image2.png"),
        require("../../assets/service_car/image3.png"),
        require("../../assets/service_car/image4.png"),
        ],
        timer: null,
        currentIndex: 0
      };
    },
    mounted: function() {
      this.startSlide();
    },
    methods: {
      startSlide: function() {
        this.timer = setInterval(this.next, 3000);
      },
      next: function() {
        this.currentIndex += 1;
      },
      prev: function() {
        this.currentIndex -= 1;
      }
    },
    computed: {
      currentImg: function() {
        return this.images[Math.abs(this.currentIndex) % this.images.length];
      }
    }
  };
  </script>
  
  <style lang="scss">
  @import './services.scss';
  </style>