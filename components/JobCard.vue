<template>
  <div class="elevation-3">
    <v-toolbar flat color="deep-orange" class="lighten-1" dark dense>
      <v-toolbar-title class="headline font-weight-thin">{{company}}</v-toolbar-title>
    </v-toolbar>

    <div class="pa-4" :class="{'grey darken-3': dark}">
      <v-layout row class="mb-3">
        <v-flex class="title font-weight-thin">{{title}}</v-flex>
        <v-flex class="title font-weight-thin text-xs-right grey--text">{{dateRange}}</v-flex>
      </v-layout>

      <v-divider/>

      <ul class="subheading mt-3 font-weight-thin" v-for="project in projects">
        <li>{{project}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'JobCard',

  props: {
    company: {
      required: true,
      type: String
    },
    title: {
      required: true,
      type: String
    },
    dateRange: {
      required: true,
      type: String
    },
    projects: {
      required: true,
      type: Array
    }
  },

  computed: {
    ...mapState({
      dark: state => state.App.dark
    })
  }
}
</script>

<style scoped>
</style>
