<template>
  <v-col style="padding: 0px">
    <v-card class="cover-picture" style="border-radius: 0px">
      <v-container style="padding: 0px; height: 300px; position: relative">
        <v-file-input
          hide-input
          prepend-icon="mdi-camera"
          style="position: absolute; bottom: 10px; right: 10px"
        ></v-file-input>
      </v-container>
    </v-card>
    <v-container style="padding: 0px; margin-bottom: 50px">
      <v-col
        class="content-container"
        style="
          background-color: white;
          border: 2px solid #e8e8e8;
          position: relative;
        "
      >
        <div
          class="profile-picture"
          style="
            border-radius: 100px;
            background-color: whitesmoke;
            position: absolute;
            border: 5px solid white;
          "
        ></div>
        <div class="py-4 flex justify-center" style="color: black">
          <div class="bio-indent">
            <p
              class="text-h5 text-md-h4"
              style="font-weight: 600; margin-bottom: 6px"
            >
              Lorem Ipsum
            </p>
            <div class="d-flex">
              <p
                class="text-subtitle2 text-md-h6 mr-6"
                style="font-weight: 400"
              >
                Lorem, Ipsum
              </p>
              <p
                class="text-subtitle2 text-md-h6 mr-6"
                style="font-weight: 400"
              >
                Lorem
              </p>
              <p
                class="text-subtitle2 text-md-h6 mr-6"
                style="font-weight: 400"
              >
                01/01/2001
              </p>
            </div>
          </div>
          <p class="text-body-1" style="font-weight: 400">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
            praesentium deleniti, vero a quod quaerat enim sint. Consequaturg
            recusandae totam vero blanditiis, tempora nihil exercitationem
            maxime sapiente cupiditate consequuntur quo!
          </p>
        </div>
        <div
          class="bio-details-container"
          style="color: black; display: flex; margin-bottom: 30px"
        >
          <div class="bio-details-item bio-details-item1">
            <div
              style="
                display: flex;
                flex-direction: row;
                justify-content: space-between;
              "
            >
              <p class="text-h5" style="font-weight: 600; margin-bottom: 0px">
                Experience
              </p>
              <v-icon color="blue">mdi-plus</v-icon>
            </div>

            <div
              style="
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
              "
            >
              <p class="text-body-1" style="color: silver; padding: 30px">
                Add your experience now
              </p>
              <div
                style="
                  background-color: whitesmoke;
                  width: 100%;
                  border-radius: 8px;
                  padding: 14px 20px;
                  margin-bottom: 16px;
                  display: flex;
                  flex-direction: row;
                  justify-content: start;
                  align-items: center;
                "
              >
                <div
                  style="
                    width: 70px;
                    height: 70px;
                    background: linear-gradient(to top right, #06f5f9, #f906f5);
                    opacity: 0.5;
                    margin-right: 10px;
                  "
                ></div>
                <div>
                  <p class="text-h6" style="font-weight: 600; margin-bottom: 0">
                    Employee
                  </p>
                  <p class="text-body2" style="margin-bottom: 0">
                    Finfolk Network
                  </p>
                  <p class="text-body2" style="margin-bottom: 0">
                    1 Jan 2019 - 1 Jan 2020
                  </p>
                </div>
              </div>
              <div
                style="
                  background-color: whitesmoke;
                  width: 100%;
                  border-radius: 8px;
                  padding: 14px 20px;
                "
              >
                <p class="text-h6" style="font-weight: 600">
                  Add New Experience
                </p>
                <v-text-field light placeholder="Company Name" />
                <v-text-field light placeholder="Starting From" />
                <v-text-field light placeholder="Ending In" />
                <div
                  style="
                    display: flex;
                    justify-content: flex-end;
                    width: 100%;
                    margin-top: 20px;
                  "
                >
                  <v-btn
                    color="primary"
                    elevation="2"
                    style="margin-right: 8px"
                  >
                    <v-icon color="#fff">mdi-content-save</v-icon> Save
                  </v-btn>
                  <v-btn color="accent" elevation="2">Cancel</v-btn>
                </div>
              </div>
            </div>
          </div>
          <div class="bio-details-item bio-details-item2">
            <div
              style="
                display: flex;
                flex-direction: row;
                justify-content: space-between;
              "
            >
              <p class="text-h5" style="font-weight: 600; margin-bottom: 0px">
                Education
              </p>
              <v-icon color="blue">mdi-plus</v-icon>
            </div>
            <div
              style="
                display: flex;
                justify-content: center;
                align-items: center;
                flex-direction: column;
              "
            >
              <p class="text-body-1" style="color: silver; padding: 30px">
                Add your education now
              </p>
              <div
                style="
                  background-color: whitesmoke;
                  width: 100%;
                  border-radius: 8px;
                  padding: 14px 20px;
                  margin-bottom: 16px;
                  display: flex;
                  flex-direction: row;
                  justify-content: start;
                  align-items: center;
                "
              >
                <div
                  style="
                    width: 70px;
                    height: 70px;
                    background: linear-gradient(to top right, #06f5f9, #f906f5);
                    opacity: 0.5;
                    margin-right: 10px;
                  "
                ></div>
                <div>
                  <p class="text-h6" style="font-weight: 600; margin-bottom: 0">
                    Purwadhika
                  </p>
                  <p class="text-body2" style="margin-bottom: 0">
                    Graduated at:
                  </p>
                  <p class="text-body2" style="margin-bottom: 0">1 Jan 2019</p>
                </div>
              </div>
              <div
                style="
                  background-color: whitesmoke;
                  width: 100%;
                  border-radius: 8px;
                  padding: 14px 20px;
                "
              >
                <p class="text-h6" style="font-weight: 600">
                  Add New Education
                </p>
                <v-text-field light placeholder="School Name" />
                <v-text-field light placeholder="Graduated At" />
                <div
                  style="
                    display: flex;
                    justify-content: flex-end;
                    width: 100%;
                    margin-top: 20px;
                  "
                >
                  <v-btn
                    color="primary"
                    elevation="2"
                    style="margin-right: 8px"
                  >
                    <v-icon color="#fff">mdi-content-save</v-icon> Save
                  </v-btn>
                  <v-btn color="accent" elevation="2">Cancel</v-btn>
                </div>
              </div>
            </div>
          </div>
        </div>
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
            <div
              style="
                aspect-ratio: 1;
                border-radius: 8px;
                background-color: whitesmoke;
              "
            >
              contoh foto
            </div>
            <div
              style="
                aspect-ratio: 1;
                border-radius: 8px;
                background-color: whitesmoke;
              "
            >
              contoh foto
            </div>
            <div
              style="
                background-color: whitesmoke;
                border-radius: 8px;
                aspect-ratio: 1;
                display: flex;
                justify-content: center;
                align-items: center;
                cursor: pointer;
              "
            >
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
      </v-col>
    </v-container>
  </v-col>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style>
.cover-picture {
  height: 300px;
}

.profile-picture {
  height: 200px;
  width: 200px;
  top: -80px;
  left: 30px;
}

.content-container {
  padding: 25px;
}

.bio-indent {
  padding-left: 230px;
}

.bio-details-container {
  flex-direction: row;
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

.album-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
}

@media (min-width: 600px) and (max-width: 800px) {
  .cover-picture {
    height: 250px;
  }

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

  .bio-details-container {
    flex-direction: column;
  }

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

  .album-container {
    grid-template-columns: repeat(3, 1fr);
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

  .bio-details-container {
    flex-direction: column;
  }

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

  .album-container {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
