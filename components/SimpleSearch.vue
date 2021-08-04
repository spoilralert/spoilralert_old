<template>
  <ais-instant-search
    :search-client="searchClient"
    index-name="dev_spoilrmovies"
  >
    <ais-search-box />
    <ais-hits>
      <div slot="item" slot-scope="{ item }">
        <div style="float: left; margin: 10px">
          <img :src="item.image" height="100px" width="100px" />
        </div>
        <div style="float: right">
          <h2>{{ item.title }}</h2>
          <h4>{{ item.releaseYear }}</h4>
        </div>
      </div>
    </ais-hits>
  </ais-instant-search>
</template>
<script lang="ts">
import Vue from 'vue'
import algoliasearch from 'algoliasearch/lite'
import 'instantsearch.css/themes/satellite.css'

export default Vue.extend({
  data() {
    return {
      searchClient: algoliasearch('ASKPQVVCKC', ''),
    }
  },
})
</script>

<style>
body {
  font-family: sans-serif;
  padding: 1em;
}
</style>