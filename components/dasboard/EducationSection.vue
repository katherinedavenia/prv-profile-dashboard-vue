<template>
  <div class="col-center">
    <p
      v-if="!educationIsOpen && !education"
      class="text-body-1"
      style="color: silver; padding: 30px"
    >
      Add your education now
    </p>
    <div v-if="educationIsOpen" class="add-item-container">
      <p class="text-h6" style="font-weight: 600">Add New Education</p>
      <slot></slot>
      <div class="button-end">
        <v-btn color="primary" elevation="2" @click="submitEducation">
          <v-icon color="#fff">mdi-content-save</v-icon> Save
        </v-btn>
      </div>
    </div>
    <div v-if="school_name && graduation_time" class="item-container">
      <div class="gradient-square"></div>
      <div>
        <p class="text-h6" style="font-weight: 600; margin-bottom: 0">
          {{ school_name }}
        </p>
        <p class="text-body2" style="margin-bottom: 0">Graduated at:</p>
        <p class="text-body2" style="margin-bottom: 0">
          {{ graduation_time }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'EducationSection',
  props: {
    educationIsOpen: {
      type: Boolean,
      default: false,
    },
    education: {
      type: Object,
      default: () => {},
    },
    submitEducation: {
      type: Function,
      default: () => {},
    },
  },
}
</script>

<style>
.row-between {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.col-center {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.item-container {
  background-color: whitesmoke;
  width: 100%;
  border-radius: 8px;
  padding: 14px 20px;
  margin-bottom: 16px;
  display: flex;
  flex-direction: row;
  justify-content: start;
  align-items: center;
}

.gradient-square {
  width: 70px;
  height: 70px;
  background: linear-gradient(to top right, #06f5f9, #f906f5);
  opacity: 0.5;
  margin-right: 10px;
}

.add-item-container {
  background-color: whitesmoke;
  width: 100%;
  border-radius: 8px;
  padding: 14px 20px;
  margin: 16px 0;
}

.button-end {
  display: flex;
  justify-content: flex-end;
  width: 100%;
  margin-top: 20px;
}

.bio-details-item {
  width: 50%;
  margin-bottom: 16px;
  display: flex;
  flex-direction: column;
}

.bio-details-item1 {
  margin-right: 16px;
}

.bio-details-item2 {
  margin-left: 16px;
}

@media (min-width: 600px) and (max-width: 800px) {
  .bio-details-item {
    width: 100%;
    margin-bottom: 32px;
  }

  .bio-details-item1 {
    margin-right: 0px;
  }

  .bio-details-item2 {
    margin-left: 0px;
  }
}

@media (max-width: 600px) {
  .bio-details-item {
    width: 100%;
    margin-bottom: 32px;
  }

  .bio-details-item1 {
    margin-right: 0px;
  }

  .bio-details-item2 {
    margin-left: 0px;
  }
}
</style>
