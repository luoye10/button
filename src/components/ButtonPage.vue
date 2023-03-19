<template>
  <div class="container">
    <el-row>
      <custom-button type="primary" circle>
        <div slot="a">头部</div>
        <footer slot="b">底部</footer>
      </custom-button>
      <button-size type="danger" size="small">
        <div slot="word">危险</div>
      </button-size>
      <button-plain type="success" plain>
        <div slot="text">成功</div>
      </button-plain>
      <button-round type="warning" round>
        <div slot="item">警告按钮</div>
      </button-round>
    </el-row>
  </div>
</template>
<script>
import ButtonPlain from './ButtonPlain.vue';
import ButtonSize from './ButtonSize.vue';
import CustomButton from './CustomButton.vue';
import ButtonRound from './ButtonRound.vue';
export default {
  components: {
    CustomButton,
    ButtonPlain,
    ButtonSize,
    ButtonRound,
  },
  data() {
    return {
      text: '按钮',
    };
  },
};
</script>
