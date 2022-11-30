<template>
  <div class="otp-container">
    <v-otp-input v-model="otpValue" length="4"></v-otp-input>
    <div class="button-container">
      <v-btn
        :disabled="otpValue.length < 4"
        color="primary"
        block
        @click="submitOtp"
        >Verification</v-btn
      >
    </div>
    <p
      style="
        text-decoration: underline;
        cursor: pointer;
        margin-top: 20px;
        margin-bottom: 0px;
      "
      @click="sendAgainOtp"
    >
      Resend OTP Number
    </p>
    <div class="d-flex">
      <p style="margin-right: 5px">
        Back to <nuxt-link to="login"> Login </nuxt-link>
      </p>
      <p>or <nuxt-link to="register"> Register </nuxt-link></p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      otpValue: '',
    }
  },
  methods: {
    submitOtp() {
      try {
        this.$store.dispatch('otpMatch', {
          otp: this.otpValue,
        })
      } catch (error) {
        console.log(error)
      }
    },
    sendAgainOtp() {
      try {
        this.$store.dispatch('requestSendOtp')
      } catch (error) {
        console.log(error)
      }
    },
  },
}
</script>

<style scoped>
.otp-container {
  width: 60%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.button-container {
  margin-top: 50px;
  width: 100%;
  padding: 0 35%;
}
</style>
