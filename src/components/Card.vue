<script>
export default {
  name: "Card",
  // props: ['content']
}
</script>

<template>
  <div class="card">
    <div id="card-header">
      <slot name="header"></slot>
    </div>
    <div id="card-content">
      <slot>Default Content</slot>
    </div>
    <div id="card-footer">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  padding: 16px;
  margin-bottom: 20px;
  width: 300px;
  text-align: center;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
</style>