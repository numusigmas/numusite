<template>
  <v-app light>
    <v-toolbar dark color="rgb(12,50,164)" clipped-left>
      <v-toolbar-side-icon
        class="hidden-md-and-up"
        @click.stop="drawer = !drawer"
      ></v-toolbar-side-icon>
      <v-toolbar-title class="white--text">NuMu Sigmas</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
          v-for="(item, i) in items"
          :key="i"
          class="white--text"
          :to="item.to"
          flat
          exact
          >{{ item.title }}</v-btn
        >
      </v-toolbar-items>
    </v-toolbar>

    <v-navigation-drawer
      id="drawer"
      v-model="drawer"
      temporary
      absolute
      width="200"
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon> {{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-content>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; NuMu Sigmas 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'home',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'info',
          title: 'About Us',
          to: '/about'
        },
        {
          icon: 'fas fa-users',
          title: 'Current Members',
          to: '/current'
        },
        {
          icon: ' fas fa-user-graduate',
          title: 'Alumni',
          to: '/alumni'
        },
        {
          icon: 'fas fa-clipboard-list',
          title: 'Competitions',
          to: '/competitions'
        },
        {
          icon: 'fas fa-calendar',
          title: 'Events',
          to: '/events'
        },
        {
          icon: 'fas fa-credit-card',
          title: 'Donate',
          to: '/donate'
        }
      ],
      miniVariant: true,
      right: true,
      rightDrawer: null,
      title: 'Vuetify.js'
    }
  }
}
</script>
