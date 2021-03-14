<template>
  <section
    id="about"
    class="overflow-hidden"
  >
    <v-row
      class="primary"
      no-gutters
    >
      <v-col
        class="pa-5"
        cols="12"
        md="6"
      >
        <base-bubble-1 style="transform: translate(5%, -5%)" />

        <base-heading class="info--text">
          {{ about.about_title }}
        </base-heading>

        <base-text class="mb-5">
          {{ about.about_description }}
        </base-text>

        <base-subheading class="info--text">
          {{ about.skills.skills_title }}
        </base-subheading>

        <base-text class="mb-5">
          {{ about.skills.skills_description }}
        </base-text>

        <v-alert
          outlined
          color="info"
        >
          <v-row style="color: #69A1BB;">
            <v-col
              class="text-uppercase"
              cols="6"
            >
              <div
                v-for="(skill, i) in about.skills.first_column"
                :key="i"
                class="mb-2"
                v-text="skill.skill_name"
              />
            </v-col>
            <v-col
              class="text-uppercase"
              cols="6"
            >
              <div
                v-for="(skill, i) in about.skills.second_column"
                :key="i"
                class="mb-2"
                v-text="skill.skill_name"
              />
            </v-col>
          </v-row>
        </v-alert>
      </v-col>

      <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/aboutme.png')"
          height="100%"
        />
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    props: {
      about: {
        type: Object,
        required: true,
      },
    },
  }
</script>
