<template>
  <h3 v-if="posts.length > 0">Список постов</h3>
  <h3 v-else>Список постов пуст</h3>
  <div class="post-list">
    <transition-group name="slide-fade">
      <post-item
          v-for="post in posts"
          :post="post"
          :key="post.id"
          @remove="this.$emit('remove', post)"
      />
    </transition-group>
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
  .slide-fade-enter-active {
    transition: all 200ms ease;
  }

  .slide-fade-leave-active {
    transition: all 200ms cubic-bezier(1, 0.5, 0.8, 1);
  }

  .slide-fade-enter-from,
  .slide-fade-leave-to {
    transform: translateX(40px);
    opacity: 0;
  }

  .slide-fade-move {
    transition: transform 200ms ease;
  }
</style>