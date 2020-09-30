<template>
  <v-theme-provider dark>
    <base-section
      id="contact-us"
      class="primary"
      space="40"
    >
      <base-heading
        :space="$vuetify.breakpoint.mdAndUp ? 0 : 4"
        title="Our Latest Projects"
      />
      <v-row justify="center">
        <v-col
          v-for="(src, index) in imgs"
          :key="index"
          @click="() => showImg(index)"
          md="4"
        >
          <v-img
            :src="src.src"
            height="300"
          />
        </v-col>
      </v-row>
      <vue-easy-lightbox
        :visible="visible"
        :imgs="imgs"
        :index="index"
        @hide="handleHide"
      ></vue-easy-lightbox>
    </base-section>
  </v-theme-provider>
</template>

<script>
  import VueEasyLightbox from 'vue-easy-lightbox'

  export default {
    name: 'SectionNews',

    provide: {
      heading: { align: 'center' },
    },

    components: {
      VueEasyLightbox,
    },
    data () {
      return {
        visible: false,
        index: 0,
        imgs: [
          {
            src: 'https://www.websitesowner.com/uploads/review/seasun.jpg',
            title: 'Sea Sun Property',
          },
          {
            src: 'https://www.websitesowner.com/uploads/review/cattleya.png',
            title: 'Cattleya Appartment',
          },
          {
            src:
              'https://www.websitesowner.com/uploads/review/Destination-Vine.jpg',
            tittle: 'Destination Vine',
          },
          {
            src: 'https://www.websitesowner.com/uploads/review/Daytona_Beach.jpg',
            title: 'Daytona Beach',
          },
          {
            src: 'https://www.websitesowner.com/uploads/review/cattleya.png',
            title: 'Cattleya Appartment',
          },
          {
            src:
              'https://images.freeimages.com/images/large-previews/176/mansion-in-the-canyon-1575490.jpg',
            title: 'this is title',
          },
        ],
      }
    },
    methods: {
      showImg (index) {
        this.index = index
        this.visible = true
      },
      handleHide () {
        this.visible = false
      },
      show () {
        this.visible = true
      },
    },
  }
</script>
