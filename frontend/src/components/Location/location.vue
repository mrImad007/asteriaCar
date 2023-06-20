<template>
    <div>
      <a href="#">
      <transition-group name="fade" tag="div" >
        <div v-for="i in [currentIndex]" :key="i" class="location">
          <a href="">
            <font size="+10" id="LocationH1"><strong>Location de voiture</strong></font>
          </a>
          <img :src="currentImg" />
        </div>
    </transition-group>
      </a>
    </div>
  </template>
  
  <script>
  export default {
    name: "locationComponent",
    data() {
      return {
        images: [
        require("../../assets/location_car/image1.png"),
        require("../../assets/location_car/image2.png"),
        require("../../assets/location_car/image3.png"),
        require("../../assets/location_car/image4.png"),
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
  @import './location.scss';
  </style>