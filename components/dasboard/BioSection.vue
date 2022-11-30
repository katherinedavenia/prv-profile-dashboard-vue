<template>
  <div class="py-4 flex justify-center" style="color: black">
    <slot></slot>
    <div class="button-end" style="margin-bottom: 50px">
      <v-btn color="primary" elevation="2" @click="submitBiodata">
        <v-icon color="#fff">mdi-content-save</v-icon> Save
      </v-btn>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BioSection',
  props: {
    submitBiodata: {
      type: Function,
      default: () => {},
    },
  },
}
</script>
