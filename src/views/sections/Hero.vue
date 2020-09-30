<template>
  <section id="hero">
    <div>
      <v-carousel hide-delimiters>
        <v-carousel-item
          v-for="(item,i) in items"
          :key="i"
          :src="item.src"
          :reverse-transition="item.reversetransition"
          :transition="item.transition"
        >
          <v-row
            class="fill-height"
            align="center"
            justify="center"
          >
            <div class="display-3">
              <v-responsive
                class="d-flex align-center mx-0"
                height="100%"
                max-width="700"
                width="100%"
              >
                <base-heading :title="item.heading" />

                <base-body class="">
                  {{ item.content }}
                </base-body>
                <div
                  :class="$vuetify.breakpoint.smAndDown ? 'flex-column align-start' : 'align-center'"
                  class="d-flex flex-wrap"
                >
                  <base-btn>
                    Discover More
                  </base-btn>
                </div>
              </v-responsive>
            </div>
          </v-row>
        </v-carousel-item>
      </v-carousel>
    </div>
  </section>
</template>

<!--<script>
  export default {
    name: 'SectionHero',

    provide: {
      theme: { isDark: true },
    },

    computed: {
      minHeight () {
        const height = this.$vuetify.breakpoint.mdAndUp ? '100vh' : '50vh'

        return `calc(${height} - ${this.$vuetify.application.top}px)`
      },
    },
  }
</script>-->
<script>
  export default {
    data () {
      return {
        colors: [
          'primary',
          'secondary',
          'yellow darken-2',
          'red',
          'orange',
        ],
        model: 0,
        items: [
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
            heading: 'BEST E-COMERCE WEBSITE',
            content: 'we Design the unique design for every website',
            transition: 'scale-transition',
            reversetransition: 'scroll-y-transition',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
            heading: 'BEST E-COMERCE WEBSITE',
            content: 'we Design the unique design for every website',
            transition: 'scale-transition',
            reversetransition: 'scroll-y-transition',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
            heading: 'BEST E-COMERCE WEBSITE',
            content: 'we Design the unique design for every website',
            transition: 'scale-transition',
            reversetransition: 'scroll-y-transition',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
            heading: 'BEST E-COMERCE WEBSITE',
            content: 'we Design the unique design for every website',
            transition: 'scale-transition',
            reversetransition: 'scroll-y-transition',
          },
        ],
      }
    },
  }
</script>
