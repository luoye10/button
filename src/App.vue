<template>
  <div id="app">
    <ButtonPage @button-click="appClick" @page-click="conClick"></ButtonPage>
  </div>
</template>

<script>
import ButtonPage from './components/ButtonPage';

export default {
  name: 'App',
  data() {
    return {
      word: '',
    };
  },
  components: {
    ButtonPage,
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
