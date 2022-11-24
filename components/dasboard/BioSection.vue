<template>
  <div class="py-4 flex justify-center" style="color: black">
    <slot></slot>
    <div class="buttons-group" style="margin-bottom: 50px">
      <v-btn color="primary" elevation="2" style="margin-right: 8px">
        <v-icon color="#fff">mdi-content-save</v-icon> Save
      </v-btn>
      <v-btn color="accent" elevation="2">Cancel</v-btn>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BioSection',
}
</script>
