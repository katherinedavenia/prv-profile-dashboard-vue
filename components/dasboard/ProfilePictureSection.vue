<template>
  <div
    class="profile-picture"
    :class="{ 'default-profile': !user_picture }"
  ></div>
</template>

<script>
export default {
  name: 'ProfilePictureSection',
  props: {
    user_picture: {
      type: Object,
      default: () => {},
    },
  },
}
</script>

<style scoped>
.profile-picture {
  height: 200px;
  width: 200px;
  top: -80px;
  left: 30px;
  border-radius: 100px;
  position: absolute;
  border: 5px solid white;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.default-profile {
  background-image: url('https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/socialmedia/apple/155/monkey-face_1f435.png');
}

@media (min-width: 600px) and (max-width: 800px) {
  .profile-picture {
    height: 180px;
    width: 180px;
    left: 20px;
  }
}

@media (max-width: 600px) {
  .profile-picture {
    height: 150px;
    width: 150px;
    left: 16px;
  }
}
</style>
