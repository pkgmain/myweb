<template>
  <v-app v-cloak :dark="dark">
    <v-btn icon @click="toggleDark">
      <v-icon>invert_colors</v-icon>
    </v-btn>
    <v-content>
      <nuxt/>
    </v-content>
  </v-app>
</template>

<script>
import { mapState } from 'vuex'

export default {
  methods: {
    toggleDark() {
      this.$store.commit('App/toggleDark')
    }
  },

  computed: {
    ...mapState({
      dark: state => state.App.dark
    })
  }
}
</script>
