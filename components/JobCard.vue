<template>
  <div class="elevation-3">
    <v-toolbar flat color="deep-orange" class="lighten-1" dark dense>
      <v-toolbar-title class="headline font-weight-thin">{{company}}</v-toolbar-title>
    </v-toolbar>

    <div class="pa-4" :class="{'grey darken-3': dark}">
      <v-layout row class="mb-3">
        <v-flex class="title font-weight-thin">{{position}}</v-flex>
        <v-flex class="title font-weight-thin text-xs-right grey--text">{{start}} - {{end}}</v-flex>
      </v-layout>

      <v-divider/>

      <ul class="subheading mt-3 font-weight-thin" v-for="highlight in highlights">
        <li>{{highlight}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import { mapState } from "vuex";
import dateFns from "date-fns";

export default {
  name: "JobCard",

  props: {
    company: {
      required: true,
      type: String
    },
    position: {
      required: true,
      type: String
    },
    startDate: {
      required: true,
      type: String
    },
    endDate: {
      required: false,
      type: String
    },
    highlights: {
      required: true,
      type: Array
    }
  },

  computed: {
    start() {
      return dateFns.format(this.startDate, "MMM YYYY")
    },
    end() {
      if (!this.endDate) {
        return "Present"
      }

      return dateFns.format(this.endDate, "MMM YYYY")
    },
    ...mapState({
      dark: state => state.App.dark
    })
  }
};
</script>

<style scoped>
</style>
