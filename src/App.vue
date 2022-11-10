<template>
  <div class="app">
    <h3>Страница с постами</h3>
    <button @click="showDialog" class="dialog__show-button btn">Создать пост</button>
    <my-dialog v-model:show="dialogVisible">
      <post-form
          @create="createPost"
      />
    </my-dialog>

    <post-list
      :posts="posts"
      @remove="deletePost"
      v-if="!isPostLoading"
    />
    <h3 v-else>Зашрузка данных...</h3>
  </div>
</template>

<script>
import PostForm from "@/Components/PostForm.vue";
import PostList from "@/Components/PostList.vue";
import MyDialog from "@/Components/UI/MyDialog.vue";

export default {
  components: {
    PostForm,
    PostList,
    MyDialog
  },

  data() {
    return {
      title: "",
      body: "",
      posts: [],
      dialogVisible: false,
      isPostLoading: false
    }
  },

  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },

    deletePost(post) {
      this.posts = this.posts.filter(item => item.id !== post.id);
    },

    showDialog() {
      this.dialogVisible = true;
    },

    fetchPosts() {
      let url = "https://jsonplaceholder.typicode.com/posts?_limit=10"

      try {
        this.isPostLoading = true;
        fetch(url)
            .then(response => response.json())
            .then(response => {
              this.posts= response;
            })
      } catch(error) {
          alert("Ошибка загрузки постов")
      } finally {
          this.isPostLoading = false;
      }
    }
  },

  mounted() {
    this.fetchPosts();
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

  .dialog__show-button {
    margin: 15px 0;
  }

  @media (max-width: 1120px) {
    .app {
      width: unset;
    }
  }
</style>