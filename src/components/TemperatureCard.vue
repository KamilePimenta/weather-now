<template>
  <div class="card" :class="cityInfo.humidity ? 'main' : ''">
    <header class="card__header">{{ cityInfo.location }}</header>
    <div class="card__body" :class="temperatureColor">{{ cityInfo.temperature }}º</div>
    <footer class="card__footer">
      <template v-if="cityInfo.humidity">
        <div class="card__footer-info">
          <div>
            <span>Humidity</span>
            <strong>{{ cityInfo.humidity }}</strong>
          </div>
          <div>
            <span>Pressure</span>
            <strong>{{ cityInfo.pressure }}</strong>
          </div>
        </div>
      </template>
      <small class="card__footer-update">{{ cityInfo.update }}</small>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'TemperatureCard',
  props: {
    cityInfo: { type: Object, required: true },
  },
  computed: {
    temperatureColor() {
      const value = this.cityInfo.temperature;
      if (value <= 5) return 'blue';
      if (value > 25) return 'red';
      return 'orange';
    },
  },
};
</script>

<style scoped>
.card {
  width: 100%;
  max-width: 300px;
  margin: 15px 30px;
  background-color: #fff;
  color: #b4b4b4;
  text-align: center;
  border-radius: 10px;
  box-shadow: 2px 2px 4px rgba(0,0,0,.15);
  overflow: hidden;
  order: 1;
}

.card.main {
  order: 0;
}

@media screen and (min-width: 764px) {
  .card,
  .card.main {
    order: initial;
  }
}

.card__header,
.card__footer {
  min-height: 40px;
  padding: 10px 20px;
}

.card__header {
  border-bottom: 1px solid #ebebeb;
}

.card__body {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 30px 0;
  font-size: 60px;
  font-weight: bold;
}

.card__body.blue {
  color: #69a3ff;
}

.card__body.orange {
  color: #ff9632;
}

.card__body.red {
  color: #ed1946;
}

.card__footer {
  background-color: #f1f1f1;
}

.card__footer-update {
  font-size: 12px;
}

.card__footer-info {
  display: flex;
  align-items: flex-start;
  justify-content: space-evenly;
  margin-bottom: 15px;
  font-size: 14px;
}

.card__footer-info span {
  display: block;
  margin-bottom: 5px;
  text-transform: uppercase;
}

.card__footer-info strong {
  color: #737c84;
  font-weight: 400;
}
</style>
