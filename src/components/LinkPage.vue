<template>
  <div class="container">
    <custom-link type="primary" underline>
      <div slot="text">主要连接</div>
    </custom-link>
    <custom-link type="success">
      <div slot="text">成功连接</div>
    </custom-link>
    <custom-link type="warning">
      <div slot="text">警告连接</div>
    </custom-link>
    <custom-link type="danger">
      <div slot="text">危险连接</div>
    </custom-link>
    <custom-link type="info" disabled>
      <div slot="text">信息连接</div>
    </custom-link>
  </div>
</template>
<script>
import CustomLink from './CustomLink.vue';
export default {
  components: { CustomLink },
};
</script>
