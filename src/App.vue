<template>
  <div id="app">
    <ButtonPage @button-click="appClick" @page-click="conClick"></ButtonPage>
    <link-page></link-page>
  </div>
</template>

<script>
import ButtonPage from './components/ButtonPage';
import LinkPage from './components/LinkPage.vue';

export default {
  name: 'App',
  data() {
    return {
      word: '',
    };
  },
  components: {
    ButtonPage,
    LinkPage,
  },
  methods: {
    appClick(m, n) {
      console.log(m, n);
    },
    conClick(str) {
      console.log(str);
    },
  },
};
</script>

<style>
</style>
