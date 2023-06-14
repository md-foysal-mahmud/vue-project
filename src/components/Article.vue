<script>
export default {
  name: "Article",
  props: {
    title: {
      type: String,
      required: true,
      default: 'Unknown Title'
    },
    likes: Number
  },
  inheritAttrs: false
}
</script>

<template>
  <!-- <div id="article-id"> -->
  <div>
    <h2 v-bind="$attrs">Article Title: {{ title }}</h2>
    <h5>Likes: {{ likes }}</h5>
  </div>
</template>