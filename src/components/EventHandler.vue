<script>
export default {
  name: "EventHandler",
  data() {
    return {
      name: "Foysal",
      count: 0
    }
  },
  methods: {
    increment(num, event) {
      this.count += num;
      console.log('Event', event);
    },
    decrement(num) {
      this.count -= num;
    }
  }
}
</script>

<template>
  <h2>{{ name }}</h2>
  <div>
    <button v-on:click="name = 'Prince'">Change Name</button> 
    <button v-on:mouseover="name = 'Mahmud'">Change Name on mouse hover</button>
    <h2>{{ count }}</h2>
    <button v-on:click="count++">Increment count by 1</button>
    <button v-on:click="count--">Decrement count by 1</button>
    <hr>
    <button v-on:click="increment(5, $event)">Increment Function calling</button>
    <button v-on:click="decrement(2)">Decrement Function calling</button>
  </div>
</template>