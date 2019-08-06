<template>
  <Map />
</template>

<script>
import Map from './components/Map.vue'

export default {
    components: {
    Map
  }
}
</script>

<style>
  body { margin:0; padding:0; }
  #map { position:absolute; top:0; bottom:0; width:100%; }
</style>
