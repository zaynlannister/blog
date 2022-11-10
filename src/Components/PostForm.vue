<template>
  <h3>Создание поста</h3>
  <div class="action">
    <input v-model="post.title" class="input" type="text" placeholder="введите заголовок">
    <input v-model="post.body" class="input action-inp" type="text" placeholder="введите содержимое">
    <button @click="createPost" class="btn action-btn">Создать</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: ""
      }
    }
  },

  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);

      this.post = {
        title: '',
        body: ''
      }
    }
  }
}
</script>

<style scoped lang="scss">
  .action {
    display: flex;
    flex-direction: column;
    padding: 10px 0;

  &-inp {
     margin: 15px 0;
   }

  &-btn {
     align-self: flex-end;
   }
  }
</style>