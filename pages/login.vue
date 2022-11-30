<template>
  <div class="form-container">
    <h1 style="margin-bottom: 50px; line-height: 1.1">
      It's good to see you back!<br />Login to your profile now
    </h1>
    <form-auth type="login" />
  </div>
</template>

<script>
import FormAuth from '../components/auth/FormAuth.vue'
export default {
  name: 'LoginPage',
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
