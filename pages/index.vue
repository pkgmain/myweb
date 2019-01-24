<template>
  <v-layout row wrap>
    <v-flex lg4>
      <v-layout column align-center mb-2>
        <v-avatar size="150" class="elevation-5 mb-2">
          <img src="/avatar.jpg"/>
        </v-avatar>

        <div class="headline font-weight-thin">{{resume.basics.name}}</div>
        <div class="subheading font-weight-thin">Full Stack Software Developer</div>
        <div class="subheading font-weight-thin mb-2">Favorite Tools</div>
        <v-layout row wrap justify-around class="px-4" style="width: 100%;">
          <v-flex class="text-xs-center">
            <img src="/gopher.png" alt="Go" height="30px;">
            <div class="subheading font-weight-thin">Go</div>
          </v-flex>

          <v-flex class="text-xs-center">
            <img src="/vue_logo.png" alt="Vue" style="height: 30px;">
            <div class="subheading font-weight-thin">Vue</div>
          </v-flex>

          <v-flex class="text-xs-center">
            <img src="/flutter_logo.png" alt="Flutter" style="height: 30px;">
            <div class="subheading font-weight-thin">Flutter</div>
          </v-flex>

          <v-flex class="text-xs-center">
            <img src="/kotlin_logo.png" alt="Kotlin" style="height: 30px;">
            <div class="subheading font-weight-thin">Kotlin</div>
          </v-flex>
        </v-layout>
      </v-layout>
    </v-flex>

    <v-flex lg8 class="px-5">
      <v-layout column>
        <template v-for="job in resume.work">
          <job-card
            class="mb-3"
            :company="job.company"
            :position="job.position"
            :start-date="job.startDate"
            :end-date="job.endDate"
            :highlights="job.highlights"
          />
        </template>
      </v-layout>
    </v-flex>
  </v-layout>
</template>
<script>
import JobCard from "../components/JobCard";
import resume from "../static/resume.json";

export default {
  components: { JobCard },
  computed: {
    resume() {
      return resume;
    }
  }
};
</script>
