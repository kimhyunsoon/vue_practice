<template>
  <div class="userRegistWrap">
    <div class="verticalWrap top">
      <p class="mainTitle">[OOO] 전문가<br>주식정보 알리미를<br>시작합니다.</p>
      <p class="subTitle">부제목입니다.</p>
    </div>
    <div class="verticalWrap mid">
    </div>
    <div class="verticalWrap bot">
      <div class="checkBoxWrap">
        <v-checkbox
          v-model="checkbox"
        >
        </v-checkbox>
        <p><a @click="dialog = true; checkbox = false">서비스 이용약관</a>에 동의합니다.</p>
        <template>
          <div class="text-center">
            <v-dialog
              v-model="dialog"
              width="500"
            >
              <v-card>
                <v-card-title class="text-h7">
                  서비스 이용약관
                </v-card-title>

                <v-card-text>
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                  이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플 이용약관 샘플
                </v-card-text>

                <v-divider></v-divider>

                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                    color="primary"
                    @click="dialog = false"
                  >
                    동의하고 시작하기
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
          </div>
        </template>
      </div>
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
    checkbox: false,
    dialog: false,
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
