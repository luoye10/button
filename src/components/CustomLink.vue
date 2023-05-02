<template>
  <div :class="[customClass, 'link']">
    <slot name="text"></slot>
  </div>
</template>
<script>
export default {
  name: 'CustomLink',
  props: {
    type: {
      type: String,
      default: 'info',
    },
    disabled: Boolean,
    underline: Boolean,
  },
  computed: {
    customClass() {
      let classList = [];
      if (this.type) {
        classList.push(this.type);
      }
      if (this.disabled) {
        classList.push('disabled');
      }
      if (this.underline) {
        classList.push('underline');
      }
      return classList;
    },
  },
};
</script>
<style lang="less" scoped>
.link {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  margin: 10px;
}
.primary {
  color: blue;
}
.success {
  color: green;
}
.warning {
  color: orange;
}
.danger {
  color: red;
}
.info {
  color: grey;
}
.disabled {
  cursor: not-allowed;
}
.underline {
  text-decoration: underline;
}
</style>
