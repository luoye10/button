<template>
  <button :class="[type, size]">
    <slot name="word"></slot>
  </button>
</template>
<script>
export default {
  props: {
    type: {
      type: String,
      default: '',
    },
    size: {
      type: String,
      default: '',
    },
  },
};
</script>
<style>
.danger {
  background: red;
  margin: 0 10px;
  color: white;
  border-radius: 5px;
}
.mini {
  height: 30px;
}
.small {
  height: 40px;
}
.medium {
  height: 50px;
}
</style>
