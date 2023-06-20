<template>
  <div class="main">
    <locationComponent class="AppLocation"></locationComponent>
    <servicesComponent class="AppService"></servicesComponent>
    
  </div>
</template>

<script>
import locationComponent from './components/Location/location.vue';
import servicesComponent from './components/Services/services.vue';


export default {
  name: "App",
  components: {
    locationComponent,
    servicesComponent
  }
};
</script>

<style>

.main{
  display: flex;
  width: max-content;
  height: max-content;
}
.AppService{
  margin-left: -212px;
}
.AppLocation{
  margin-left: -10px;
}
/* .LocationLogo{
  position: absolute;
  background-color: white;
}
.ServicesLogo{
  position: absolute;
  top: 70%;
  right: 10%;
  background-color: white;
} */
</style>
