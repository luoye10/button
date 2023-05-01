<template>
  <button
    :class="[customClass, 'btn', { dis: disabled || loading }]"
    @click="sendClick"
    :disabled="disabled || loading"
  >
    <loading-icon v-if="loading" class="icon"></loading-icon>
    <slot name="b"></slot>
  </button>
</template>

<script>
import LoadingIcon from '@/assets/loadingIcon.vue';
export default {
  components: {
    LoadingIcon,
  },
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
    circle: Boolean,
    plain: Boolean,
    round: Boolean,
    loading: Boolean,
    disabled: Boolean,
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
      if (this.loading) {
        cls.push('loading');
      }
      if (this.disabled) {
        cls.push('disabled');
      }
      return cls;
    },
  },
};
</script>

<style lang="less" scoped>
.btn {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  width: 100px;
  height: 50px;
  font-size: 16px;
  border-radius: 5px;
  margin: 0 10px;
  color: white;
}
.primary {
  background: #6cf;
}
.circle {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}
.danger {
  background: red;
}
.success {
  background: green;
}
.plain {
  color: blue;
  border-color: blue;
  background: rgba(209, 209, 253, 0.685);
}
.warning {
  background: orange;
}
.round {
  border-radius: 30px;
}
.mini {
  width: 50px;
  height: 30px;
}
.small {
  width: 80px;
  height: 40px;
}
.medium {
  width: 120px;
  height: 50px;
}
.loading {
  .icon {
    margin-right: 10px;
    animation: a 2s linear infinite;
  }
}
@keyframes a {
  0% {
    transform: rotate(0);
  }
  100% {
    transform: rotate(360deg);
  }
}
.dis {
  cursor: not-allowed;
}
</style>
