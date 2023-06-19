<template>
  <div class="main">
    <locationComponent></locationComponent>
    <servicesComponent class="AppService"></servicesComponent>
  </div>
</template>

<script>
import locationComponent from './components/location.vue';
import servicesComponent from './components/services.vue';


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
}
.AppService{
  margin-left: -212px;
}
</style>
