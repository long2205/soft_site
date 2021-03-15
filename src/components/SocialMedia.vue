<template>
  <div>
    <v-btn
      v-for="(item, i) in items.slice(0, large ? items.length : 2)"
      :key="i"
      fab
      class="ma-2"
      color="green"
      :href="item.link"
      target="_blank"
      :small="!large"
    >
      <v-icon
        dark
        v-text="item.icon"
      />
    </v-btn>
    <v-btn
      fab
      class="ma-2"
      color="green"
      :small="!large"
      @click="toMail"
    >
      <v-icon
        mdi-email
        v-text="'mdi-email'"
      />
    </v-btn>
  </div>
</template>

<script>
  export default {
    props: {
      large: {
        type: Boolean,
        default: false,
      },
    },

    data: () => ({
      items: [
        {
          name: 'Facebook',
          icon: 'mdi-linkedin',
          link: 'https://www.linkedin.com/in/thanh-long-hoang-a2309a1a9/',
        },
        {
          name: 'Instagram',
          icon: 'mdi-instagram',
          link: 'https://www.instagram.com/llq2205/',
        },
      ],
    }),

    methods: {
      toMail () {
        document.getElementById('get-in-touch').scrollIntoView({
          top: 0,
          left: 0,
          behavior: 'smooth',
        })
      },
    },
  }
</script>
