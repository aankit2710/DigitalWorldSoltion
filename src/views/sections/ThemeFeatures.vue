<template>
  <base-section id="theme-features">
    <base-section-heading title="Our Services">
    </base-section-heading>

    <v-container>
      <v-row>
        <v-col
          v-for="(feature, i) in features"
          :key="i"
          cols="12"
          md="4"
        >
          <base-avatar-card
            v-bind="feature"
            align="left"
            horizontal
          >
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis illum veniam cum dolores ratione commodi beatae quas maxime, laboriosam excepturi solut!
          </base-avatar-card>
        </v-col>
      </v-row>
    </v-container>
  </base-section>
</template>

<script>
  export default {
    name: 'SectionThemeFeatures',

    data: () => ({
      features: [
        {
          color: 'primary',
          dark: true,
          title: 'Web Design',
          icon: 'mdi-fountain-pen-tip',
        },
        {
          title: 'Responsive Design',
          icon: 'mdi-cellphone',
        },
        {
          color: 'primary',
          dark: true,
          title: 'Clean Coding',
          icon: 'mdi-pencil-box-outline',
        },
        {
          title: 'Smarter Solutions',
          icon: 'mdi-image-size-select-actual',
        },
        {
          color: 'primary',
          dark: true,
          title: 'Seo Optimized',
          icon: 'mdi-ice-pop',
        },
        {
          title: '24/7 Support',
          icon: 'mdi-help-circle-outline',
        },
      ],
    }),
  }
</script>
