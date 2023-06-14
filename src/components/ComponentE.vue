<script>
export default {
  name: "ComponentE",
  inject: ['username']
}
</script>

<template>
  <h2>Component E username is: {{ username }}</h2>
</template>