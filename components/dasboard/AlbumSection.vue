<template>
  <div
    style="
      color: black;
      display: flex;
      flex-direction: column;
      margin-bottom: 30px;
    "
  >
    <p
      class="text-h5"
      style="font-weight: 600; margin-bottom: 0px; margin-bottom: 16px"
    >
      Photo Album
    </p>
    <div class="album-container">
      <div class="photo">contoh foto</div>
      <div class="photo">contoh foto</div>
      <div class="add-photo-button">
        <v-icon
          large
          color="whitesmoke"
          style="
            background-color: gainsboro;
            border-radius: 50px;
            padding: 14px;
          "
          >mdi-plus</v-icon
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AlbumSection',
  props: {
    userPictures: {
      type: Array,
      default: () => [],
    },
  },
}
</script>

<style scoped>
.album-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
}

.photo {
  aspect-ratio: 1;
  border-radius: 8px;
  background-color: whitesmoke;
}

.add-photo-button {
  background-color: whitesmoke;
  border-radius: 8px;
  aspect-ratio: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

@media (min-width: 600px) and (max-width: 800px) {
  .album-container {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 600px) {
  .album-container {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
