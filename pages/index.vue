<template>
  <v-col style="padding: 0px">
    <cover-section />
    <v-container style="padding: 0px; margin-bottom: 50px">
      <v-col class="content-container">
        <profile-picture-section />
        <bio-section :submit-biodata="submitBiodata">
          <div class="bio-indent">
            <v-text-field
              v-model="userData.name"
              placeholder="Name"
              class="mt-0 pt-0"
              light
            />
            <div class="bio-flex-d">
              <v-text-field
                v-model="userData.hometown"
                class="mt-0 pt-0 mr-6"
                placeholder="Town"
                light
              />
              <v-text-field
                v-model="userData.gender"
                class="mt-0 pt-0 mr-6"
                placeholder="Gender"
                light
              />
              <v-text-field
                v-model="userData.birthday"
                placeholder="Birthday"
                class="mt-0 pt-0"
                light
              />
            </div>
          </div>
          <v-textarea
            v-model="userData.bio"
            class="mt-0 pt-0"
            placeholder="Bio"
            light
          />
        </bio-section>
        <div class="bio-flex-d" style="color: black; margin-bottom: 30px">
          <div class="bio-details-item bio-details-item1">
            <div class="row-between">
              <p class="text-h5" style="font-weight: 600; margin-bottom: 0px">
                Experience
              </p>
              <v-icon
                color="blue"
                style="width: 25px; height: 25px"
                @click="experienceIsOpen = !experienceIsOpen"
                >mdi-plus</v-icon
              >
            </div>
            <experience-section
              :submit-experience="submitExperience"
              :experience-is-open="experienceIsOpen"
              :career="career"
            >
              <v-text-field
                v-model="userData.career.company_name"
                light
                placeholder="Company Name"
              />
              <v-text-field
                v-model="userData.career.starting_from"
                light
                placeholder="Starting From"
              />
              <v-text-field
                v-model="userData.career.ending_in"
                light
                placeholder="Ending In"
              />
            </experience-section>
          </div>
          <div class="bio-details-item bio-details-item2">
            <div class="row-between">
              <p class="text-h5" style="font-weight: 600; margin-bottom: 0px">
                Education
              </p>
              <v-icon
                color="blue"
                style="width: 25px; height: 25px"
                @click="educationIsOpen = !educationIsOpen"
                >mdi-plus</v-icon
              >
            </div>
            <education-section
              :submit-education="submitEducation"
              :education-is-open="educationIsOpen"
              :education="education"
            >
              <v-text-field
                v-model="userData.education.school_name"
                light
                placeholder="School Name"
              />
              <v-text-field
                v-model="userData.education.graduation_time"
                light
                placeholder="Graduated At"
              />
            </education-section>
          </div>
        </div>
        <album-section />
      </v-col>
    </v-container>
  </v-col>
</template>

<script>
import CoverSection from '../components/dasboard/CoverSection.vue'
import ProfilePictureSection from '../components/dasboard/ProfilePictureSection.vue'
import BioSection from '../components/dasboard/BioSection.vue'
import ExperienceSection from '../components/dasboard/ExperienceSection.vue'
import EducationSection from '../components/dasboard/EducationSection.vue'
import AlbumSection from '../components/dasboard/AlbumSection.vue'

export default {
  name: 'IndexPage',
  components: {
    CoverSection,
    ProfilePictureSection,
    BioSection,
    ExperienceSection,
    EducationSection,
    AlbumSection,
  },
  middleware: 'auth',
  data() {
    return {
      userData: {
        name: '',
        hometown: '',
        gender: '',
        birthday: '',
        bio: '',
        career: {
          company_name: '',
          starting_from: '',
          ending_in: '',
        },
        education: {
          school_name: '',
          graduation_time: '',
        },
        cover_picture: {
          url: '',
        },
        user_picture: {
          picture: {
            url: '',
          },
        },
        user_pictures: [],
      },
      experienceIsOpen: false,
      educationIsOpen: false,
    }
  },
  computed: {
    users() {
      return this.$store.getters.getUser
    },
    basic: {
      get() {
        return this.$store.getters.getUser
      },
    },
  },
  watch: {
    users(newValue) {
      this.userData = JSON.parse(JSON.stringify(newValue))
    },
  },
  mounted() {
    this.$store.dispatch('profile')
  },
  methods: {
    submitBiodata() {
      this.$store
        .dispatch('dashboard/biodata', {
          name: this.userData.name,
          birthday: this.userData.birthday,
          hometown: this.userData.hometown,
          bio: this.userData.bio,
        })
        .catch((err) => {
          console.error(err.response)
        })
    },
    submitExperience() {
      this.$store
        .dispatch('dashboard/experience', {
          company_name: this.userData.career.company_name,
          starting_from: this.userData.career.starting_from,
          ending_in: this.userData.career.ending_in,
        })
        .catch((err) => {
          console.error(err.response)
        })
    },
    submitEducation() {
      this.$store
        .dispatch('dashboard/education', {
          school_name: this.userData.education.school_name,
          graduation_time: this.userData.education.graduation_time,
        })
        .catch((err) => {
          console.error(err.response)
        })
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
  background-color: whitesmoke;
  position: absolute;
  border: 5px solid white;
}

.content-container {
  padding: 25px;
  background-color: white;
  border-right: 2px solid #e8e8e8;
  border-left: 2px solid #e8e8e8;
  border-bottom: 2px solid #e8e8e8;
  position: relative;
}

.bio-indent {
  padding-left: 230px;
}

.bio-flex-d {
  display: flex;
  flex-direction: row;
}

@media (min-width: 600px) and (max-width: 800px) {
  .profile-picture {
    height: 180px;
    width: 180px;
    left: 20px;
  }

  .content-container {
    padding: 20px;
  }

  .bio-indent {
    padding-left: 0px;
    padding-top: 80px;
  }

  .bio-flex-d {
    flex-direction: column;
  }
}

@media (max-width: 600px) {
  .profile-picture {
    height: 150px;
    width: 150px;
    left: 16px;
  }

  .content-container {
    padding: 16px;
  }

  .bio-indent {
    padding-left: 0px;
    padding-top: 50px;
  }

  .bio-flex-d {
    flex-direction: column;
  }
}
</style>
