<template>
  <v-theme-provider dark>
    <section id="hero-alt">
      <base-img
        :height="$vuetify.breakpoint.mdAndUp ? 350 : 225"
        :src="src"
        color="#45516b"
        flat
        max-width="100%"
        tile
      >
        <v-row
          v-if="title"
          align="center"
          class="ma-0 fill-height text-center"
          justify="center"
        />
      </base-img>
      <div class="card-row">
        <div
          v-for="(card, index) in cards"
          :key="index"
          :ref="`card_${index}`"
          class="card"
          @mouseover="hoverCard(index)"
          @mouseout="hoverCard(-1)"
        >
          <img
            class="card-image"
            :class="{'selected': isSelected(index)}"
            :src="card.image"
          >
          <div class="card-footer">
            <h3 class="card-title">
              {{ card.title }}
            </h3>
            <p class="card-text">
              by
              <span
                class="card-author"
                :class="{'selected': isSelected(index)}"
              >
                {{ card.author }}
              </span>
            </p>
          </div>
        </div>
      </div>
    </section>
  </v-theme-provider>
</template>

<script>
  // Components
  import {
    HexToRGBA,
    RGBAtoCSS,
  } from 'vuetify/lib/util/colorUtils'

  export default {
    name: 'SectionHeroAlt',

    metaInfo () {
      return {
        changed: meta => (this.title = meta.titleChunk.toUpperCase()),
      }
    },

    provide: {
      heading: { align: 'center' },
    },

    data: () => ({
      title: '',
    }),

    computed: {
      gradient () {
        const color = `${this.$vuetify.theme.themes.light.secondary}CC`
        const overlay = RGBAtoCSS(HexToRGBA(color))

        return `to top, ${overlay}, ${overlay}`
      },
      src () {
        return 'https://www.signs365.com/portal/static/images/promos/banner.jpg'
      },
      items () {
        return [
          { text: 'HOME', to: '/' },
          { text: this.title },
        ]
      },
    },
  }
</script>

<style lang="sass">
  #hero-alt
    .v-breadcrumbs__item
      color: #FFFFFF
</style>
