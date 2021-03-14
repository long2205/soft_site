<template>
  <div>
    <welcome v-bind:welcome="data.welcome"></welcome>

    <certificates v-bind:certificates_and_careers="data.certificates_and_careers"></certificates>

    <!-- <careers v-bind:careers="data.careers"></careers> -->

    <about-me v-bind:about="data.about"></about-me>

    <get-in-touch v-bind:contact="data.contact"></get-in-touch>
  </div>
</template>

<script>
  import data from '@/data/lang.js'
  export default {
    name: 'CoreView',

    data: () => ({
      data: data.en,
    }),

    components: {
      AboutMe: () => import('@/components/AboutMe'),
      GetInTouch: () => import('@/components/GetInTouch'),
      Certificates: () => import('@/components/Certificates'),
      // Careers: () => import('@/components/Careers'),
      Welcome: () => import('@/components/Welcome'),
    },
  }
</script>
