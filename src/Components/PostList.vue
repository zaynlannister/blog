<template>
  <h3>Список постов</h3>
  <div class="post-list">
    <post-item
      v-for="post in posts"
      :post="post"
    />
  </div>
</template>

<script>
import PostItem from "@/Components/PostItem.vue";

export default {
  components: {
    PostItem,
  },

  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

</style>