<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <div class="text-center">
        <logo />
        <vuetify-logo />
      </div>
      <v-card>
        <v-card-title class="headline">
          Welcome to the Vuetify + Nuxt.js template
        </v-card-title>
        <v-card-text v-show="loading">
          Connecting to Github to find Phalcon Version
        </v-card-text>
        <v-card-text v-show="!loading">
          Our latest Phalcon Version is: {{ version }} <br />
          <code>
            {{ body }}
          </code>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn color="primary" nuxt to="/inspire">
            Continue
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data() {
    return {
      version: '0',
      body: '',
      loading: true
    }
  },
  async mounted() {
    const response = await this.$axios.$get(
      'https://api.github.com/repos/phalcon/cphalcon/releases'
    )
    this.loading = false
    this.version = response[0].name
    this.body = response[0].body
    console.log(response)
  }
}
</script>
