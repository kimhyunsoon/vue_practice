<template>
  <div class="userRegistWrap">
    <div class="verticalWrap top">
      <p class="mainTitle">[OOO] 전문가<br>주식정보 알리미를<br>시작합니다.</p>
      <p class="subTitle">부제목입니다.</p>
    </div>
    <div class="verticalWrap mid"></div>
    <div class="verticalWrap bot">
      <v-btn color="primary" block class="confirmBtn">
        시작하기
      </v-btn>
    </div>
  </div>
</template>

<script>
// import TestCom from './TestCom.vue';
export default {
  name: 'UserRegist',

  data: () => ({
    message: 'ㅎㅇㅎㅇ',
    test: true,
  }),
  methods: {
    reverseMessage() {
      this.message = this.message.split('').reverse().join('');
    },
  },
  components: {
  },
};
</script>
<style lang="scss" scoped>
  .userRegistWrap{
    display:flex;
    flex-wrap:wrap;
    padding:1.5rem;
    font-family:'noto sans kr';
    height:100vh;
    align-content:space-between;
    *{
      margin:0;
      padding:0;
      letter-spacing:-.7px;
    }
    .verticalWrap{
      width:100%;
      &.bot{
        .confirmBtn{
          font-size:1rem;
          height:3rem;
          border-radius:100px;
        }
      }
    }
    .mainTitle{
      font-size:1.4rem;
      width:100%;
      margin-top:2rem;
      font-weight:500;
      &+.subTitle{
        margin-top:.4rem;
      }
    }
    .subTitle{
      font-size:1.1rem;
      color:#aaa;
      font-weight:300;
    }
  }
</style>
