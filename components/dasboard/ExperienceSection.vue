<template>
  <div class="col-center">
    <p
      v-if="!experienceIsOpen && !career"
      class="text-body-1"
      style="color: silver; padding: 30px"
    >
      Add your experience now
    </p>
    <div v-if="experienceIsOpen" class="add-item-container">
      <p class="text-h6" style="font-weight: 600">Add New Experience</p>
      <slot></slot>
      <div class="button-end">
        <v-btn color="primary" elevation="2" @click="submitExperience">
          <v-icon color="#fff">mdi-content-save</v-icon> Save
        </v-btn>
      </div>
    </div>
    <div
      v-if="company_name && starting_from && ending_in"
      class="item-container"
    >
      <div class="gradient-square"></div>
      <div>
        <p class="text-h6" style="font-weight: 600; margin-bottom: 0">
          Employee
        </p>
        <p class="text-body2" style="margin-bottom: 0">{{ company_name }}</p>
        <p class="text-body2" style="margin-bottom: 0">
          {{ starting_from }} - {{ ending_in }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ExperienceSection',
  props: {
    experienceIsOpen: {
      type: Boolean,
      default: false,
    },
    career: {
      type: Object,
      default: () => {},
    },
    submitExperience: {
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
  margin: 16px 0px;
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
