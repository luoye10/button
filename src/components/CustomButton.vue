<template>
  <button :class="customClass" @click="sendClick">
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
    size: {
      type: String,
      default: '',
    },
    circle: {
      type: Boolean,
      default: false,
    },
    plain: Boolean,
    round: Boolean,
  },
  methods: {
    sendClick() {
      this.$emit('custom-click', 10, 20);
    },
  },
  computed: {
    customClass() {
      let cls = [];
      if (this.type) {
        cls.push(this.type);
      }
      if (this.circle) {
        cls.push('circle');
      }
      if (this.size) {
        cls.push(this.size);
      }
      if (this.round) {
        cls.push('round');
      }
      if (this.plain) {
        cls.push('plain');
      }
      return cls;
    },
  },
};
</script>

<style lang="less" scoped>
.primary {
  background: #6cf;
  color: white;
}
.circle {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}
.danger {
  background: red;
  margin: 0 10px;
  color: white;
  border-radius: 5px;
}
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
.warning {
  background: orange;
  color: white;
}
.round {
  border-radius: 30px;
  padding: 10px;
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
