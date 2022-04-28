<template>
  <main>
    <TemperatureCard v-for="weather in mockInfo" :cityInfo="weather" :key="weather.id"/>
  </main>
</template>

<script>
import TemperatureCard from './TemperatureCard.vue';

const mockInfo = [
  {
    id: 1,
    location: 'Nuuk, GL',
    temperature: -4,
    humidity: '',
    pressure: '',
    update: 'Update at 02:48:27 PM',
  },
  {
    id: 2,
    location: 'Urubici, BR',
    temperature: 19,
    humidity: '75%',
    pressure: '892hPa',
    update: 'Update at 02:48:27 PM',
  },
  {
    id: 3,
    location: 'Nairobi, KE',
    temperature: 31,
    humidity: '',
    pressure: '',
    update: 'Update at 02:48:27 PM',
  },
];

export default {
  name: 'Home',
  components: { TemperatureCard },
  props: {
    msg: String,
  },
  data() {
    return {
      mockInfo,
    };
  },
};
</script>

<style scoped>
main {
  display: flex;
  justify-content: center;
  align-items: stretch;
  flex-wrap: wrap;
  min-height: 100vh;
  padding: 75px 0 15px;
}

@media screen and (min-width: 764px) {
  main {
    align-items: center;
  }
}
</style>
