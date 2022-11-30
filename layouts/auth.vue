<template>
  <v-app>
    <v-main class="auth-container">
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'BlogLayout',
}
</script>

<style>
.auth-container {
  height: 100vh;
  background: linear-gradient(90deg, #cce5cf 0%, #c3cfe5 100%);
}
</style>
