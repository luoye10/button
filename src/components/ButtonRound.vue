<template>
  <button :class="[type, round ? 'round' : '']">
    <slot name="item"></slot>
  </button>
</template>
<script>
export default {
  props: {
    type: {
      type: String,
      default: '',
    },
    round: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
<style>
.warning {
  background: orange;
  color: white;
}
.round {
  border-radius: 30px;
  padding: 10px;
}
</style>
