<template>
  <div class="container">
      <Navigation />
      <router-view />
  </div>
</template>

<script>
import Navigation from './components/Navigation.vue'
export default {
  components: { Navigation },
  data() {
    return {
    }
  },
  methods: {
  }
}
</script>

<style>

</style>