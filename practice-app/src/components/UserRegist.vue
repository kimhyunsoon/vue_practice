<template>
  <div class="userRegistWrap">
    <div class="verticalWrap top">
      <p class="mainTitle">[OOO] 전문가<br>주식정보 알리미를<br>시작합니다.</p>
      <p class="subTitle">{{message}}</p>
      <v-btn v-on:click="subTopic()">구독</v-btn>
      <v-btn v-on:click="cancleTopic()">구독취소</v-btn>
      <v-btn v-on:click="sendSMS()">sendSMS</v-btn>
      <v-btn v-on:click="checkSMS()">checkSMS</v-btn>
      <v-btn v-on:click="codeSent()">codeSent</v-btn>
      <v-btn v-on:click="signIn()">signIn</v-btn>
      <v-btn v-on:click="receiveTestFunc()">receiveTestFunc</v-btn>

      <v-text-field v-model="code" label="code"></v-text-field>
      <v-text-field v-model="verificationId" label="ver"></v-text-field>
      <v-btn v-on:click="codeLog()">값 확인</v-btn>

    </div>
    <div class="verticalWrap mid">
    </div>
    <div class="verticalWrap bot">
      <div class="checkBoxWrap">
        <v-switch
          v-model="checkbox"
          inset
        ></v-switch>
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
import { FCM } from '@capacitor-community/fcm';
import { cfaSignInPhone } from 'capacitor-firebase-auth';
import { cfaSignInPhoneOnCodeSent, cfaSignInPhoneOnCodeReceived } from 'capacitor-firebase-auth';
import { User } from 'firebase/app'
import { cfaSignIn } from 'capacitor-firebase-auth';


// let user = new User();

export default {
  name: 'UserRegist',

  data: () => ({
    message: 'ㅎㅇㅎㅇ',
    checkbox: false,
    dialog: false,
    code: '123',
    verificationId:'verificationId',
  }),
  methods: {
    reverseMessage() {
      this.message = this.message.split('').reverse().join('');
    },

    subTopic() {
      FCM.subscribeTo({ topic: 'test' }).then(() => alert('subscribed to topic'));
    },
    cancleTopic() {
      FCM.unsubscribeFrom({ topic: 'test' }).then(() => alert('unsubscribed from topic'));
    },
    sendSMS() {
      cfaSignInPhone('+821084439554').subscribe(
        user => console.log(user.phoneNumber)
      )
    },
    codeSent() {
      cfaSignInPhoneOnCodeSent().subscribe(
        verificationId => console.log(verificationId)
      )
    },
    signIn(){
      cfaSignIn('phone', {phone:'+821084439554'}).subscribe(
        user => console.log(user)
      )
    },
    receiveTestFunc(){
      cfaSignInPhoneOnCodeReceived()
      .subscribe({verificationId: this.verificationId, verificationCode: this.code})
    },
    codeLog() {
      console.log(this.code)
      console.log(this.verificationId)
    },
    checkSMS() {
      cfaSignInPhone('+821084439554', '123456')
      .subscribe(user=>{
        console.log(user)
      })  
    },

  },
  components: {
  },
};
</script>
