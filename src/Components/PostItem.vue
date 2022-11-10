<template>
  <div class="post">
    <div><strong>Название:</strong> {{ post.title }}</div>
    <div><strong>Содиржимое:</strong> {{ post.body }}</div>
  </div>
</template>

<script>
export default {
  props: {
    post: Object,
  }
}
</script>

<style scoped>

</style>