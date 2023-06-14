<script>
export default {
  name: "ComponentPropsPractices",
  props: [ 'name', 'company']
}
</script>

<template>
  <h2>Hello {{ name }} from {{ company }}</h2>
</template>