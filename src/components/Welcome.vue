<template>
  <section
    id="welcome"
    class="overflow-hidden"
  >
    <v-row no-gutters>
      <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/welcome.jpg')"
          height="100vh"
        />
      </v-col>

      <v-col
        class="align-content-space-between layout wrap"
        cols="12"
        md="6"
        :pa-5="$vuetify.breakpoint.smAndDown"
      >
        <base-bubble-1
          style="transform: rotate(5deg) translateY(25%)"
        />

        <v-row
          align="center"
          justify="center"
        >
          <v-col
            cols="10"
            md="6"
          >
            <base-heading>{{ welcome.hello }}</base-heading>
            <base-text>
              {{ welcome.hello_description }}<br>
              {{ welcome.hello_description_2 }}
            </base-text>
            <base-btn
              class="mt-4"
              @click="readMore"
            >
              {{ welcome.learn_more }}
            </base-btn>
          </v-col>
        </v-row>

        <base-bubble-2
          style="transform: rotate(180deg) translate(-200px, -15%)"
        />
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    props: {
      welcome: {
        type: Object,
        required: true,
      },
    },
    methods: {
      readMore () {
        document.getElementById('certificates').scrollIntoView({
          top: 0,
          left: 0,
          behavior: 'smooth',
        })
      },
    },
  }
</script>
