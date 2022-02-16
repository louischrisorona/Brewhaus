<template>
  <v-container>
    <div v-for="beer in beers" :key="beer.id">
      <v-card elevation="2" outlined shaped>
        <h2>{{ beer.name }}</h2>
        <v-img
          alt="displayed beer"
          class="shrink mr-2"
          contain
          src="`${beer.image_url}`"
          transition="scale-transition"
          width="40"
        />
        <p>{{ beer.description }}</p>
        <span>Food pairings</span>
        <ul>
          <li v-for="(index, food) in beer.food_pairing" :key="index">{{food}}</li>
        </ul>
        <p>ABV: {{ beer.abv }}</p>
        <v-card-actions>Beer Me</v-card-actions>
      </v-card>
    </div>
  </v-container>
</template>

<script>
  export default {
    name: 'Brewhaus',
  }
</script>
