<script>
export default {
  name: "Popup",
  emits: ['close']
}
</script>

<template>
  <div>
    <h2>This is a Popup</h2>
    <button @click="$emit('close', 'ByeBye')">Close Popup</button>
  </div>
</template>