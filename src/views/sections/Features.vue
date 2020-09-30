<template>
  <v-container class="pa-4 text-center">
    <v-row
      class="fill-height"
      align="center"
      justify="center"
    >
      <template
        v-for="(item, i) in items"
      >
        <v-col
          :key="i"
          cols="12"
          md="4"
        >
          <v-hover
            v-slot:default="{ hover }"
          >
            <v-card
              class="mx-auto"
              color="grey lighten-4"
              max-width="600"
            >
              <v-img
                :aspect-ratio="16 / 9"
                :src="item.img"
              >
                <v-card-title
                  class="title white--text"
                >
                  <v-row
                    class="fill-height flex-column"
                    justify="space-between"
                  >
                    <p
                      class="mt-4 subheading text-center display-1"
                    >
                      {{ item.title }}
                    </p>
                  </v-row>
                </v-card-title>
                <v-expand-transition>
                  <div v-if="hover">
                    <div
                      class="d-flex transition-fast-in-fast-out orange darken-2 v-card--reveal display-4 white--text"
                      style="height: 100%"
                    >
                      <v-img
                        :aspect-ratio="8 / 9"
                        :src="item.img"
                      />
                    </div>
                    <div
                      class="d-flex transition-fast-in-fast-out orange darken-2 v-card--reveal-2 display-4 white--text"
                      style="height: 100%"
                    >
                      <div>
                        <p class="ma-0 body-1 font-weight-bold text-center">
                          {{ item.text }}
                        </p>
                        <p
                          class="caption font-weight-medium font-italic text-center"
                        >
                          {{ item.subtext }}
                        </p>
                      </div>
                    </div>
                  </div>
                </v-expand-transition>
              </v-img>
            </v-card>
          </v-hover>
        </v-col>
      </template>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      items: [
        {
          icons: 'mdi-rewind',
          title: 'New Releases',
          text: 'It is New Release Friday',
          subtext: 'Newly released songs. Updated daily.',
          img: 'http://lorempixel.com/output/nightlife-q-c-640-480-5.jpg',
        },
        {
          icons: 'mdi-rewind',
          title: 'Rock',
          text: 'Greatest Rock Hits',
          subtext: 'Lose yourself in rock tunes.',
          img:
            'https://images.unsplash.com/photo-1498038432885-c6f3f1b912ee?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2100&q=80',
        },
        {
          icons: 'mdi-rewind',
          title: 'Mellow Moods',
          text: 'Ambient Bass',
          subtext: 'Chill beats to mellow you out.',
          img: 'http://lorempixel.com/output/abstract-q-c-640-480-6.jpg',
        },
        {
          icons: 'mdi-rewind',
          title: 'New Releases',
          text: 'It is New Release Friday',
          subtext: 'Newly released songs. Updated daily.',
          img: 'http://lorempixel.com/output/nightlife-q-c-640-480-5.jpg',
        },
        {
          icons: 'mdi-rewind',
          title: 'Rock',
          text: 'Greatest Rock Hits',
          subtext: 'Lose yourself in rock tunes.',
          img:
            'https://images.unsplash.com/photo-1498038432885-c6f3f1b912ee?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2100&q=80',
        },
        {
          icons: 'mdi-rewind',
          title: 'Mellow Moods',
          text: 'Ambient Bass',
          subtext: 'Chill beats to mellow you out.',
          img: 'http://lorempixel.com/output/abstract-q-c-640-480-6.jpg',
        },
      ],
      transparent: 'rgba(255, 255, 255, 0)',
    }),
  }
</script>

<style scoped>
.v-card {
  transition: opacity 0.4s ease-in-out;
}

.v-card:not(.on-hover) {
  opacity: 0.6;
}

.show-btns {
  color: rgba(255, 255, 255, 1) !important;
}

.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  position: absolute;
  left: 0;
  opacity: 1;
  width: 50%;
}
.v-card--reveal-2 {
  align-items: center;
  bottom: 0;
  justify-content: center;
  position: absolute;
  right: 0;
  opacity: 1;
  width: 50%;
}
</style>
