<template>
  <v-layout row wrap>
    <v-flex lg4>
      <v-layout column align-center mb-2>
        <v-avatar size="150" class="elevation-5 mb-2">
          <img src="/avatar.jpg"/>
        </v-avatar>

        <div class="headline font-weight-thin">Shaunn Barron</div>
        <div class="subheading font-weight-thin">Full Stack Software Developer</div>
        <div class="subheading font-weight-thin mb-2">Favorite Tools</div>
        <v-layout row wrap justify-around class="px-4" style="width: 100%;">
          <v-flex class="text-xs-center">
            <img src="/gopher.png" alt="Go" height="30px;">
            <div style="text-align: center;">Go</div>
          </v-flex>

          <v-flex class="text-xs-center">
            <img src="/vue_logo.png" alt="Vue" style="height: 30px;">
            <div style="text-align: center;">Vue</div>
          </v-flex>

          <v-flex class="text-xs-center">
            <img src="/flutter_logo.png" alt="Flutter" style="height: 30px;">
            <div style="text-align: center;">Flutter</div>
          </v-flex>

          <v-flex class="text-xs-center">
            <img src="/kotlin_logo.png" alt="Kotlin" style="height: 30px;">
            <div>Kotlin</div>
          </v-flex>
        </v-layout>
      </v-layout>
    </v-flex>

    <v-flex lg8 class="px-5">
      <v-layout column>
        <template v-for="job in jobs">
          <job-card
            class="mb-3"
            :company="job.company"
            :title="job.title"
            :date-range="job.dateRange"
            :projects="job.projects"
          />
        </template>
      </v-layout>
    </v-flex>
  </v-layout>
</template>
<script>
import JobCard from '../components/JobCard'

export default {
  components: { JobCard },
  data() {
    return {
      jobs: [
        {
          company: 'JPMorgan Chase',
          title: 'Vice President - Software Engineering',
          dateRange: '2018-02-05 - Present',
          projects: [
            "Allowance - Mobile application for managing a child's chores and funding their allowance. (Flutter, Firebase)",
            'Virtual Bank - Multi-user virtual bank environment with voice chat for the Oculus Rift. (Unity, C#)',
            'Crypto Wallet - Application for managing both hot and cold Bitcoin and Ethereum wallets and transfers. (Go, Kotlin, Spring Boot, Vue.js, PostgreSQL, Vault)',
            'iMobility - Internal social networking application with a focus on mentoring and career development. (Java, Spring Boot, Angular, MariaDB)',
            'Disputes - Application to resolve credit card disputes using Blockchain technology. (Go, Ethereum, Vue.js, PostgreSQL)'
          ]
        },
        {
          company: 'CrossChx',
          title: 'Senior Software Engineer',
          dateRange: '2016-11-14 - 2018-02-02',
          projects: [
            'Olive Manager UI - Single page web app to build and launch various workflows in AWS. (React)',
            'Olive Planner - Job Scheduler (Go, Buffalo, Vue.js)',
            'Skill Adapter - An application used to download and run any other application and upload output to S3. (Go, AWS S3, Vault)',
            'Mimic - Desktop automation software. (Node.js, Electron, OpenCV)',
            'Connect For Care Managers - Backend web services to facilitate patient care for Accountable Care Organizations. (Kotlin, Java 8, Spring Boot, MySQL, Kafka)'
          ]
        },
        {
          company: 'Fuse by Cardinal Health',
          title: 'Software Engineer',
          dateRange: '2015-08-01 - 2016-11-11',
          projects: [
            'Care Management – Single page web application and RESTful web service used by pharacists to manage patient medications. (EmberJS, Java 8, Spring Boot, Cassandra, Elasticsearch, Kafka)',
            'Alfred – Android application and RESTful web service used to manage patient medication adherence. (Java 8, Spring Boot, AngularJS, MySQL, Kafka)'
          ]
        },
        {
          company: 'NetJets (contractor via ComResource)',
          title: 'Senior Developer Analyst',
          dateRange: '2015-02-01 - 2015-08-01',
          projects: [
            'Enterprise Trip Management - Single page web application and RESTful web services used to quote, book, and manage flights. (AngularJS, Groovy, Grails, Oracle, Elasticsearch)'
          ]
        },
        {
          company: 'CrossChx',
          title: 'Software Engineer, Team Lead',
          dateRange: '2012-09-01 - 2015-02-01',
          projects: [
            'Biometric Engine – Distributed fingerprint identification application. (Java 8, Spring Boot, MySQL, RabbitMQ)',
            'SafeChx – Web application used to register patients at hospitals with a fingerprint scan. (Java Applet, Java 7, Spring MVC)',
            'Event Engine – Service to receive, archive, enrich, and process messages from hundreds of web applications. (Java 8, Spring Boot, MySQL, MongoDB, RabbitMQ)',
            'SquadChx – Android application used to identify patients in ambulances with a fingerprint and notify the hospitals with detail of the incoming patient.',
            'Mission Control – A suite of web applications used to manage external applications as well as provide real-time metrics and reports. (Java 8, Spring Boot, MySQL, Redis, RabbitMQ)',
            'Zero Gravity – Android application to be used by healthcare sales reps to locate clients via search, maps, and augmented reality. Also displayed product information.',
            'Caching Engine – Service to initialize and maintain a Redis cache. (Java 8, Spring Boot, RabbitMQ, Redis)'
          ]
        },
        {
          company: 'Nationwide',
          title: 'Developer, IT Applications',
          dateRange: '2011-07-01 - 2012-09-01',
          projects: [
            'Financial Systems – A suite of applications used calculate unit values, calculate performance, and trade mutual funds. (Java 6, Struts, Oracle)'
          ]
        }
      ]
    }
  }
}
</script>
