<template>
  <base-section
    id="pro-features"
  >
    <v-img
      :src="require('@/assets/logo.svg')"
      class="mx-auto mb-8"
      max-width="128"
    />

    <base-section-heading title="Feature Comparison">
      Get <strong>Cost Effective </strong> Website Packages<br>Choose Your Best Plan For Your Business.
    </base-section-heading>

    <v-container>
      <v-row
        align="center"
        justify="center"
      >
        <v-col
          cols="12"
          md="7"
        >
          <v-simple-table>
            <thead>
              <tr>
                <th />
                <th class="body-1 font-weight-bold text-center">
                  Ideal
                </th>
                <th class="body-1 font-weight-bold text-center">
                  Standard
                </th>
              </tr>
            </thead>

            <tbody class="body-1">
              <tr
                v-for="([name, one, two], i) in features"
                :key="i"
              >
                <td v-text="name" />

                <td class="text-center font-weight-bold">
                  <template v-if="typeof one === 'boolean'">
                    <v-icon :color="one ? 'success' : 'error'">
                      mdi-{{ one ? 'check' : 'close' }}
                    </v-icon>
                  </template>

                  <template v-else>
                    {{ one }}
                  </template>
                </td>

                <td class="text-center font-weight-bold">
                  <template v-if="typeof two === 'boolean'">
                    <v-icon :color="two ? 'success' : 'error'">
                      mdi-{{ two ? 'check' : 'close' }}
                    </v-icon>
                  </template>

                  <template v-else>
                    {{ two }}
                  </template>
                </td>
              </tr>
            </tbody>
          </v-simple-table>
        </v-col>
      </v-row>
    </v-container>
  </base-section>
</template>

<script>
  export default {
    name: 'SectionProChart',

    data: () => ({
      features: [
        ['Pages', 6, 10],
        ['W3C Certified', true, true],
        ['Sync iCAL / Google Calendar', true, true],
        ['E-mail Contact Form', true, true],
        ['Search Engine Friendly', false, true],
        ['Google Map', false, true],
        ['1 Year Hosting', false, true],
        ['Price', '$599', '$799'],
      ],
    }),
  }
</script>
