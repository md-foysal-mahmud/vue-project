<script>
export default {
  name: "EventHandler",
  data() {
    return {
      name: "Foysal"
    }
  },
  methods: {

  }
}
</script>

<template>
  <h2>{{ name }}</h2>
  <div>
    <button v-on:click="name = 'Prince'">Change Name</button>
  </div>
</template>