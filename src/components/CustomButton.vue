<template>
  <button :class="[type, circle ? 'circle' : '']">
    <slot name="b"></slot>
  </button>
</template>

<script>
export default {
  name: 'CustomButton',
  props: {
    type: {
      type: String,
      default: 'info',
    },
    text: {
      type: String,
      default: '',
    },
    circle: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style>
.primary {
  background: #6cf;
  color: white;
}
.circle {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}
</style>
