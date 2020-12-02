<template>
  <div class="weather-info-container">
    <img :src="conditionImg" width="48" height="48" class="condition-icon" />
    <div class="wind-info-container">
      <i class="fas fa-wind wind-velocity-ico"></i>
      <span class="wind-velocity">{{ windVelocity }} km/h</span>
    </div>
    <div class="temperature">{{ temperature }}°C</div>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue';
export default {
  name: 'weather-info',
  props: {
    temperature: { type: Number, default: 100 },
    windVelocity: { type: Number, default: 100 },
    conditionImg: { type: String, default: '' },
  },

  setup(props) {
    return {};
    // const temperature = ref(props.temperature);
    // const windVelocity = ref(props.windVelocity);
    // const conditionImg = ref(props.conditionImg);
    // return {
    //   temperature,
    //   windVelocity,
    //   conditionImg,
    // }
  },
};
</script>

<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css');
@import url('https://fonts.googleapis.com/css2?family=PT+Sans&display=swap');

.weather-info-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.wind-velocity-ico {
  color: #c1c6ca;
  font-size: 0.8em;
  margin-right: 4px;
}
.wind-velocity {
  font-family: 'PT Sans', sans-serif;
  color: #c1c6ca;
  font-size: 0.8em;
}

.temperature {
  font-family: 'PT sans', sans-serif;
  font-size: 3.5em;
  font-weight: 700;
  color: #2a9d8f;
}
</style>
