<template>
  <div class="app">
    <post-form/>
  </div>
</template>

<script>
import PostForm from "@/Components/PostForm.vue";

export default {
  components: {
    PostForm,
  }
}
</script>

<style lang="scss">
  .app {
    width: 1120px;
    margin: 0 auto;
  }

  .input {
    outline: none;
    border: none;
    border: 1px solid #55a0ea;
    padding: 8px 15px;
    transition: 120ms all;

    &:focus {
      box-shadow: 0px 0px 14px 2px rgba(85, 160, 234, 0.2);
    }
  }

  .btn {
    cursor: pointer;
    outline: none;
    border: none;
    border: 1px solid #55a0ea;
    background-color: #ffff;
    padding: 8px 16px;
    transition: 120ms all;

    &:hover {
      color: #ffff;
      background-color: #55a0ea;
    }
  }
</style>