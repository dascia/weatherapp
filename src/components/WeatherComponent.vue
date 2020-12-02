<template>
  <weather-info-display
    :temperature="temperature"
    :windVelocity="windVelocity"
    :conditionImg="weatherImg"
  ></weather-info-display>
  <query-input @query-entered="requestWeather"></query-input>
</template>
<script lang="ts">
import { ref } from 'vue';
import WeatherInfoDisplay from './WeatherInfoDisplayComponent.vue';
import QueryInput from './QueryInputComponent.vue';

interface WeatherResponse {
  moco?: string;
}

export default {
  name: 'weather',
  components: {
    WeatherInfoDisplay,
    QueryInput,
  },
  setup() {
    const temperature = ref<number>(0);
    const windVelocity = ref<number>(0);
    const weatherImg = ref<string>('assets/sun.png');

    function requestWeather(query: string) {
      console.log('Weather requested.');
      const endpoint = 'http://api.weatherapi.com/v1/current.json?key=fa8ef599de65459aa33151257200112&q=';
      fetch(endpoint + query)
        .then(
          (response: Response) => response.json(),
          (error: Response) => console.log(error)
        )
        .then(json => {
          windVelocity.value = +json.current.wind_kph;
          temperature.value = +json.current.feelslike_c;
          console.log(temperature.value);
          weatherImg.value = json.current.condition.icon;
        });
    }

    return {
      temperature,
      windVelocity,
      weatherImg,
      requestWeather,
    };
  },
};
</script>
