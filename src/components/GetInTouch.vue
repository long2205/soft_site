<template>
  <section
    id="get-in-touch"
    class="overflow-hidden"
  >
    <v-row
      class="primary white--text"
      no-gutters
    >
      <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/contact.png')"
          height="100%"
        />
      </v-col>

      <v-col
        class="pa-5"
        cols="12"
        md="6"
      >
        <base-bubble-1 />

        <base-heading class="mb-5 info--text">
          {{ contact.contact_title }}
        </base-heading>

        <v-sheet
          color="transparent"
          max-width="600"
        >
          <v-text-field
            color="info"
            :label="contact.form_name"
            :placeholder="contact.form_name"
            solo
            flat
          />

          <v-text-field
            color="info"
            :label="contact.form_email"
            :placeholder="contact.form_email"
            solo
            flat
          />

          <v-text-field
            color="info"
            :label="contact.form_subject"
            :placeholder="contact.form_subject"
            solo
            flat
          />

          <v-textarea
            color="info"
            :label="contact.form_message"
            :placeholder="contact.form_message"
            solo
            flat
          />

          <base-btn>{{ contact.form_submit }}</base-btn>
        </v-sheet>
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    name: 'GetInTouch',

    props: {
      contact: {
        type: Object,
        required: true,
      },
    },
  }
</script>
