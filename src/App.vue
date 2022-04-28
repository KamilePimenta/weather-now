<template>
  <div id="app">
    <TheHeader />
    <Home />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import Home from './components/Home.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    Home,
  },
};
</script>
