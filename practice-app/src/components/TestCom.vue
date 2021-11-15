<template>
  <p class="testText" v-on:click="cngMsg">{{testText}}</p>
</template>

<script>
export default {
  name: 'TestCom',

  data: () => ({
    testText: '안녕하세요.',
  }),
  methods: {
    cngMsg() {
      if (this.testText === '안녕하세요.') {
        this.testText = '안녕하세요!!';
      } else {
        this.testText = '안녕하세요.';
      }
    },
  },
};
</script>
<style lang="scss" scoped>
  .testText{
    color:red;
  }
</style>
