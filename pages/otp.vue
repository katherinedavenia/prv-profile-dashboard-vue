<template>
  <div class="form-container">
    <h1 style="margin-bottom: 50px" class="">Match your OTP number</h1>
    <form-otp />
  </div>
</template>

<script>
import FormOtp from '../components/auth/FormOtp.vue'
export default {
  name: 'OtpPage',
  components: {
    FormOtp,
  },
  layout: 'auth',
}
</script>

<style scoped>
.form-container {
  color: #475266;
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
