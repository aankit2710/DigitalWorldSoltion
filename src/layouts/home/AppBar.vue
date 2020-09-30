<template>
  <div>
    <v-app-bar
      id="home-app-bar"
      app
      color="white"
      elevation="1"
      height="80"
    >
      <base-img
        :src="require('@/assets/logo_old.svg')"
        class="mr-3 hidden-xs-only"
        contain
        max-width="52"
      />

      <base-img
        :src="require('@/assets/logo_old.svg')"
        contain
        max-width="128"
      />

      <v-spacer />

      <div>
        <v-tabs
          optional
        >
          <v-tab
            v-for="(name, i) in item"
            :key="i"
            :ripple="false"
            active-class="text--primary"
            class="font-weight-bold"
            min-width="96"
            text
          >
            <v-icon>{{ name }}</v-icon>
          </v-tab>
          <v-spacer />
          <v-tab
            v-for="(name, i) in items"
            :key="i"
            :ripple="false"
            active-class="text--primary"
            class="font-weight-bold"
            min-width="96"
            text
          >
            <v-icon>{{ name }}</v-icon>
          </v-tab>
        </v-tabs>
      </div>

      <v-app-bar-nav-icon @click="drawer = !drawer" />
    </v-app-bar>

    <home-drawer
      v-model="drawer"
      :items="items2"
    />
  </div>
</template>

<script>
  export default {
    name: 'HomeAppBar',

    components: {
      HomeDrawer: () => import('./Drawer'),
    },

    data: () => ({
      drawer: null,
      item: ['mdi-bookmark-check', 'mdi-file-outline', 'mdi-file-multiple', 'mdi-magnet', 'mdi-view-dashboard', 'mdi-dashboard'],
      items: ['mdi-camera-wireless', 'mdi-cart'],
      items2: ['Home', 'About', 'Contact'],
    }),
  }
</script>

<style lang="sass">
#home-app-bar
  .v-tabs-slider
    max-width: 24px
    margin: 0 auto

    .v-tab
      &::before
        display: none
</style>
