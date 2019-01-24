<template>
  <v-flex class="text-xs-center">
    <a :href="href" target="_blank">
      <img :src="src" :alt="name" height="30px;">
      <div class="subheading font-weight-thin" :class="{ mywhite: dark }">{{name}}</div>
    </a>
  </v-flex>
</template>

<script>
import { mapState } from "vuex";

export default {
  name: "TechLogoLink",
  props: {
    src: {
      required: true,
      type: String
    },
    name: {
      required: true,
      type: String
    },
    href: {
      required: true,
      type: String
    }
  },
  computed: {
    ...mapState({
      dark: state => state.App.dark
    })
  }
};
</script>

<style lang="stylus" scoped>
  a
    text-decoration none

  .mywhite
    color #ffffff
</style>
