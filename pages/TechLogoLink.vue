<template>
  <v-flex class="text-xs-center">
    <a :href="href" target="_blank">
      <img :src="src" :alt="name" height="30px;">
      <div class="subheading font-weight-thin">{{name}}</div>
    </a>
  </v-flex>
</template>

<script>
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
  }
};
</script>

<style lang="stylus" scoped>
  a
    text-decoration none
</style>
