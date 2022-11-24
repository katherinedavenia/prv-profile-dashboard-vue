<template>
  <v-col style="padding: 0px">
    <cover-section />
    <v-container style="padding: 0px; margin-bottom: 50px">
      <v-col class="content-container">
        <profile-picture-section />
        <bio-section>
          <div class="bio-indent">
            <v-text-field v-model="userData.name" placeholder="Name" light />
            <div class="bio-flex-d">
              <v-text-field
                v-model="userData.hometown"
                class="mr-6"
                placeholder="Town"
                light
              />
              <v-text-field
                v-model="userData.gender"
                class="mr-6"
                placeholder="Gender"
                light
              />
              <v-text-field
                v-model="userData.birthday"
                placeholder="Birthday"
                light
              />
            </div>
          </div>
          <v-text-field v-model="userData.bio" placeholder="Bio" light />
        </bio-section>
        <div class="bio-flex-d" style="color: black; margin-bottom: 30px">
          <experience-section>
            <v-text-field
              v-model="userData.companyName"
              light
              placeholder="Company Name"
            />
            <v-text-field
              v-model="userData.startingFrom"
              light
              placeholder="Starting From"
            />
            <v-text-field
              v-model="userData.endingIn"
              light
              placeholder="Ending In"
            />
          </experience-section>
          <education-section>
            <v-text-field
              v-model="userData.schoolName"
              light
              placeholder="School Name"
            />
            <v-text-field
              v-model="userData.graduationTime"
              light
              placeholder="Graduated At"
            />
          </education-section>
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
  data() {
    return {
      userData: {
        name: '',
        hometown: '',
        gender: '',
        birthday: '',
        bio: '',
        experience: {
          companyName: '',
          startingFrom: '',
          endingIin: '',
        },
        education: {
          schoolName: '',
          graduationTime: '',
        },
        coverPicture: {
          url: '',
        },
        userPicture: {
          picture: {
            url: '',
          },
        },
        userPictures: [],
      },
      experienceIsOpen: false,
      educationIsOpen: false,
    }
  },
}
</script>

<style>
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
