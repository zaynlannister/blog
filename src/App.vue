<template>
  <div class="app">
    <h3>Создание поста</h3>
    <div class="app__action">
      <input class="input" type="text" placeholder="введите заголовок">
      <input class="input app__action-inp" type="text" placeholder="введите содержимое">
      <button class="btn app__action-btn">Создать</button>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
  .app {
    width: 1120px;
    margin: 0 auto;

    &__action {
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