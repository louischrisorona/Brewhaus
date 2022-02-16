<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Brewhaus logo"
          class="shrink mr-2"
          contain
          src="./assets/beer.svg"
          transition="scale-transition"
          width="40"
        />
        <span class="mr-2">Brewhaus</span>
      </div>
    </v-app-bar>

    <v-main>
      <Brewhaus />
    </v-main>
  </v-app>
</template>

<script>
import Brewhaus from './components/Brewhaus';

export default {
  name: 'App',
  components: {
    Brewhaus
  },

  data: () => ({
      beers: [],
      // baseURL: 'https://api.punkapi.com/v2/beers',
    }),

  methods: {
    async getBeers() {
      const response = await this.$http.get('https://api.punkapi.com/v2/beers')
      this.beers = response.data
    }
  },

  created() {
    this.getBeers()
  }
};
</script>
