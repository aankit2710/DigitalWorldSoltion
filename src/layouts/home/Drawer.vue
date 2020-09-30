<template>
  <v-navigation-drawer
    color="white"
    fixed
    height="93%"
    temporary
    right
    v-bind="$attrs"
    v-on="$listeners"
    style="top:80px"
  >
    <v-list
      color="white"
    >
      <v-list-item
        v-for="name in items"
        :key="name"
        :to="{ name }"
        :exact="name === 'Home'"
        color="primary"
      >
        <v-list-item-content>
          <v-list-item-title v-text="name" />
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
  export default {
    name: 'HomeDrawer',

    props: {
      items: {
        type: Array,
        default: () => ([]),
      },
    },
  }
</script>
