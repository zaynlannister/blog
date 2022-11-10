<template>
  <div class="dialog" v-if="show" @click="hideDialog">
    <div @click.stop class="dialog__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },

  methods: {
    hideDialog() {
      this.$emit("update:show", false)
    }
  }
}
</script>

<style scoped>
  .dialog {
    z-index: 1;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.5);
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    display: flex;
  }

  .dialog__content {
    width: 400px;
    margin: auto;
    background-color: #fff;
    padding: 15px;
  }
</style>