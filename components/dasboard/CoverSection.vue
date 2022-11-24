<template>
  <v-card class="cover-picture" :class="{ 'default-cover': !coverPicture }">
    <v-container style="padding: 0px; height: 300px; position: relative">
      <v-file-input
        hide-input
        prepend-icon="mdi-camera"
        style="position: absolute; bottom: 10px; right: 10px"
      ></v-file-input>
    </v-container>
  </v-card>
</template>

<script>
export default {
  name: 'CoverSection',
  props: {
    coverPicture: {
      type: Object,
      default: () => {},
    },
  },
}
</script>

<style scoped>
.cover-picture {
  height: 300px;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  box-shadow: none !important;
  border-radius: 0px;
}

.default-cover {
  background-image: linear-gradient(90deg, #e3ffe7 0%, #d9e7ff 100%);
}

@media (min-width: 600px) and (max-width: 800px) {
  .cover-picture {
    height: 250px;
  }
}

@media (max-width: 600px) {
  .cover-picture {
    height: 250px;
  }
}
</style>
