<template>
  <v-app dark>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      style="
        background-color: #f5f5f5;
        color: #475266;
        border-bottom: 2px solid #e8e8e8;
        padding: 0px;
      "
    >
      <v-container style="display: flex; align-items: center">
        <v-toolbar-title style="font-weight: 600">
          Welcome to your dashboard, {{ userData.name }}!</v-toolbar-title
        >
        <v-spacer />
        <v-btn icon @click.stop="rightDrawer = !rightDrawer">
          <v-icon color="#475266">mdi-menu</v-icon>
        </v-btn>
      </v-container>
    </v-app-bar>
    <v-main style="background-color: #f5f5f5">
      <Nuxt />
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item>
          <v-list-item-action>
            <v-icon dark> mdi-account </v-icon>
          </v-list-item-action>
          <v-list-item-title>Account</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-action>
            <v-icon dark> mdi-inbox </v-icon>
          </v-list-item-action>
          <v-list-item-title>Inbox</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-action>
            <v-icon dark> mdi-logout </v-icon>
          </v-list-item-action>
          <v-list-item-title>Sign Out</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      style="
        height: 100px;
        background-color: #dbf3f3;
        border-top: 2px solid #e8e8e8;
      "
    >
      <v-container style="display: flex; justify-content: flex-end">
        <a
          href="https://nuxtjs.org"
          target="_blank"
          style="text-decoration: none !important; color: #475266"
        >
          Powered by Nuxt.js
        </a>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  props: {
    name: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
    }
  },
  computed: {
    userData() {
      return this.$store.getters.getUser
    },
  },
}
</script>
