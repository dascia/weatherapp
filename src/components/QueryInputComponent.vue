<template>
  <input class="query-textfield" type="text" placeholder="Enter your city" @keyup.enter="queryEntered" v-model="query" />
</template>

<script lang="ts">
import { ref } from 'vue';

export default {
  name: 'query-input',
  setup(props, { emit }) {
    const emits = ['query-entered'];
    const query = ref<string>('');

    // Emits a query-entered event
    function queryEntered() {
      emit('query-entered', query.value);
    }

    return {
      query,
      queryEntered,
    };
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
.query-textfield {
  font-family: 'Roboto', sans-serif;
  min-width: 640px;
  height: 28px;
  border: 0 none #c6cdd3;
  border-bottom: 1px solid #c6cdd3;
  font-family: 'Roboto', sans-serif;
  font-size: 1em;
}

.query-textfield:focus{
  outline: none;
}

::placeholder {
  color: #c6cdd3;
  opacity: 1;
}
</style>
