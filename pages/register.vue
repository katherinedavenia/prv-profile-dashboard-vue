<template>
  <div class="form-container">
    <h1 style="margin-bottom: 50px" class="">Register Now!</h1>
    <form-auth type="register" />
  </div>
</template>

<script>
import FormAuth from '../components/auth/FormAuth.vue'
export default {
  name: 'RegisterPage',
  components: {
    FormAuth,
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
