<template>
  <h3>Создание поста</h3>
  <div class="action">
    <input class="input" type="text" placeholder="введите заголовок">
    <input class="input action-inp" type="text" placeholder="введите содержимое">
    <button class="btn action-btn">Создать</button>
  </div>
</template>

<script>
export default {

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