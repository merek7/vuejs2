<template>
  <div id="app">
    <index/>
    <heroe/>
  </div>
</template>

<script>
import index from './components/index.vue'
import heroe from './components/heroe.vue'
export default {
  name: 'App',
  components: {
    index,
    heroe

  }
}
</script>

<style>

</style>
