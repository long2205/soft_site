<template>
  <section
    id="careers"
    class="overflow-hidden"
  >
    <v-row
      class="accent"
      no-gutters
    >
      <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/services.png')"
          height="100%"
        />
      </v-col>

      <v-col
        class="text-center pa-5 info--text"
        cols="12"
        md="6"
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <v-col cols="12">
            <base-bubble-2
              style="transform: translateX(55%)"
            />
            <base-heading>
              {{ careers.careers_title }}
            </base-heading>

            <base-text class="mb-5">
              {{ careers.careers_description }}
            </base-text>
          </v-col>

          <v-col
            v-for="(career, i) in careers.careers"
            :key="i"
            class="text-center mb-3"
            md="6"
          >
            <v-avatar
              class="elevation-6 mb-2"
              color="#69A1BB"
              size="64"
              tile
            >
              <v-img
                :src="require(`@/assets/${career.icon}`)"
              />
            </v-avatar>

            <base-text>
              <div
                class="mb-2"
                v-text="career.company_name"
              />
              <h6>{{ career.timeline }}</h6>
              <div v-html="career.job_description" />
            </base-text>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    name: 'Careers',

    props: {
      careers: {
        type: Object,
        required: true,
      },
    },
  }
</script>
