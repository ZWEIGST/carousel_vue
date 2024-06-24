<template>
  <div id="app">
    <HorizontalCarousel :items="carouselItems" />
  </div>
</template>

<script>
import HorizontalCarousel from './components/HorizontalCarousel.vue';

export default {
  name: 'App',
  components: {
    HorizontalCarousel,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
</style>