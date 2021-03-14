<template>
  <section
    id="certificates"
    class="overflow-hidden"
  >
    <v-row no-gutters>
      <!-- bằng cấp -->
      <v-col
        class="text-center pa-5"
        cols="12"
        md="6"
        style="min-height: 100vh"
      >
        <base-bubble-1
          style="transform: rotate(180deg) translateX(25%)"
        />

        <base-heading>
          {{ certificates_and_careers.certificates.certificates_title }}
        </base-heading>

        <base-text class="mb-5">
          {{ certificates_and_careers.certificates.certificates_description }} <br>
          {{ certificates_and_careers.certificates.certificates_description_2 }}
        </base-text>

        <v-card color="grey lighten-4">
          <v-container class="pa-2">
            <v-row>
              <v-col md="7">
                <base-text>{{ certificates_and_careers.certificates.technical }}</base-text>
                <v-timeline dense>
                  <v-timeline-item
                    small
                    color="blue"
                    v-for="technical in certificates_and_careers.certificates.technicals"
                    :key="technical.name"
                  >
                    <div class="font-weight-bold">
                      {{technical.name}}
                    </div>
                    <h6>{{technical.date}}</h6>
                    <a
                      :href="technical.url"
                      target="_blank"
                      style="color:black"
                      class="text-decoration-underline"
                    >{{technical.info}}</a>
                  </v-timeline-item>
                </v-timeline>
              </v-col>
              <v-col>
              <base-text>{{ certificates_and_careers.certificates.language }}</base-text>
                <v-timeline dense>
                  <v-timeline-item
                    small
                    color="red"
                    v-for="language in certificates_and_careers.certificates.languages"
                    :key="language.name"
                  >
                    <div class="font-weight-bold">
                      {{language.name}}
                    </div>
                    <h6>{{language.date}}</h6>
                    <div>{{language.level}}</div>
                  </v-timeline-item>
                </v-timeline>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-col>

      <!-- công việc -->
      <v-col
        class="primary text-center pa-5"
        md="6"
        cols="12"
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
            <base-heading class="info--text">
              {{ certificates_and_careers.careers.careers_title }}
            </base-heading>

            <base-text class="mb-5">
              {{ certificates_and_careers.careers.careers_description }}
            </base-text>
          </v-col>

          <v-col
            v-for="(career, i) in certificates_and_careers.careers.careers"
            :key="career.company_name"
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
    name: 'Certificates',

    props: {
      certificates_and_careers: {
        type: Object,
        required: true,
      },
    },
  }
</script>
