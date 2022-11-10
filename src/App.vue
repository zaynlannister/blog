<template>
  <div class="app">
    <post-form
      @create="createPost"
    />
    <post-list
      :posts="posts"
      @remove="deletePost"
    />
  </div>
</template>

<script>
import PostForm from "@/Components/PostForm.vue";
import PostList from "@/Components/PostList.vue";

export default {
  components: {
    PostForm,
    PostList
  },

  data() {
    return {
      title: "",
      body: "",
      posts: [
        {id: 1, title: "murder in the store", body: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ratione, veniam!"},
        {id: 2, title: "some theme", body: "dolor sit amet, consectetur adipisicing elit. Ratione, veniam!"},
        {id: 3, title: "new action", body: "ipsum dolor sit amet, consectetur adipisicing elit. Ratione, veniam!"},
      ]
    }
  },

  methods: {
    createPost(post) {
      this.posts.push(post);
    },

    deletePost(post) {
      this.posts = this.posts.filter(item => item.id !== post.id);
    }
  }
}
</script>

<style lang="scss">
  .app {
    width: 1120px;
    margin: 0 auto;
    padding: 0 20px;
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

  .post-list {
    margin-top: 20px;
  }

  .post {
    border: 1px solid #55a0ea;
    padding: 10px 15px;
    margin-bottom: 15px;
  }

  @media (max-width: 1120px) {
    .app {
      width: unset;
    }
  }
</style>