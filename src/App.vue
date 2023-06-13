<script>
import EventHandler from './components/EventHandler.vue';
import FormHandler from './components/FormHandler.vue';
import BasicPractices from './components/BasicPractices.vue'

export default {
  components: {
    FormHandler,
    EventHandler,
    BasicPractices
  },
  name: "App",
  data() {
    return {
    }
  },
}
</script>

<template>
  <div>
    <h1>FormHandler component:</h1>
    <FormHandler />

    <br>
    <hr> 

    <h1>EventHandler component:</h1>
    <EventHandler />

    <br><br><br>
    <hr> 
    <h1>Basic Practices:</h1>
    <BasicPractices />
  </div>
</template>

<style>
#app {
  background-color: #f2f2f2; /* Gray background color */
  width: 100%;
  height: 100%; /* Set the height to fill the viewport */
  color: black;
}
</style>

