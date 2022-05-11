<template>
  <div id="app">
    <header>
      <h1>Boolfix</h1>
      <app-search/>
    </header>
    <main>
      <app-grid/>
    </main>

  </div>
</template>

<script>
import AppGrid from './components/AppGrid.vue'

import AppSearch from './components/AppSearch.vue'

export default {
  name: 'App',
  components: {
    AppSearch,
    AppGrid,
  }
}
</script>

<style lang="scss">

</style>
//200dd33df89407555d5cbb5bee067f09//
//https://api.themoviedb.org/3/movie/550?api_key=200dd33df89407555d5cbb5bee067f09