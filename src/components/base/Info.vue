<template>
  <v-theme-provider :dark="dark">
    <div>
      <base-img
        :src="require('@/assets/zero-logo-dark.svg')"
        contain
        max-width="128"
        min-height="78"
        width="100%"
      />

      <base-title
        size="body-1"
        space="4"
        title="MULTI-PURPOSE THEME"
        weight="regular"
      />

      <base-body>
        WebsitesOwner is one of the best leading company in the world. We provides top notch services to our all customers, Our expertise is in Web Development, Web Designing, Mobile Application Development. We deliver to our clients 24/7 technical and customer service support round the year.
      </base-body>

      <base-btn
        class="mb-12"
        color="white"
        outlined
      >
        More Info
      </base-btn>
    </div>
  </v-theme-provider>
</template>

<script>
  export default {
    name: 'BaseInfo',

    props: {
      title: String,
      dark: Boolean,
    },

    data: () => ({
      business: [
        {
          icon: 'mdi-map-marker-outline',
          title: 'Address',
          text: '185 Rue Du Grand Pre74520 Valleiry France Europe',
        },
        {
          icon: 'mdi-cellphone',
          title: 'Phone',
          text: ' 01 (978) 312 7557<br>44 (203) 868 1555',
        },
        {
          icon: 'mdi-email',
          title: 'Email',
          text: 'info@Websitesowner.com',
        },
      ],
    }),
  }
</script>
