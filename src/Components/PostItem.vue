<template>
  <div class="post">
    <div>
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Содиржимое:</strong> {{ post.body }}</div>
    </div>
    <button @click="this.$emit('remove', post)" class="btn">Удалить</button>
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
  .post {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>