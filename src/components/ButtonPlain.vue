<template>
  <button :class="[type, plain ? 'plain' : '']">
    <slot name="text"></slot>
  </button>
</template>
<script>
export default {
  props: {
    type: {
      type: String,
      default: '',
    },
    plain: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
<style>
.success:hover {
  background: green;
  color: white;
  cursor: pointer;
}
.plain {
  border: 1px solid green;
  color: green;
  background: greenyellow;
  margin: 0 10px;
  border-radius: 5px;
  padding: 10px;
}
</style>
