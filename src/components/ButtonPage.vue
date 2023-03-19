<template>
  <div class="container">
    <el-row>
      <custom-button type="primary" circle @custom-click="startClick">
        <div slot="a">头部</div>
        <footer slot="b">底部</footer>
      </custom-button>
      <custom-button type="danger" size="small" @custom-click="lastClick">
        <div slot="b">危险</div>
      </custom-button>
      <custom-button type="success" plain @custom-click="click">
        <div slot="b">成功</div>
      </custom-button>
      <custom-button type="warning" round>
        <div slot="b">警告按钮</div>
      </custom-button>
    </el-row>
  </div>
</template>
<script>
import CustomButton from './CustomButton.vue';
export default {
  components: {
    CustomButton,
  },
  data() {
    return {
      text: '按钮',
    };
  },
  methods: {
    startClick(a, b) {
      console.log('click', a, b);
    },
    lastClick() {
      this.$emit('button-click', true, false);
    },
    click() {
      this.$emit('page-click', 'hello');
    },
  },
};
</script>
