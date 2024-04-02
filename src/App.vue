<script setup>
  import { reactive } from 'vue';

  const division = (x, y) => {
    if (y == 0) return 'divisão por zero';
    else return x / y;
  }

  const estado = reactive({
    num_01: '0',
    num_02: '0',
    result: '',
    filter: '',
    operations: {
      sum: (x, y) => x + y,
      sub: (x, y) => x - y,
      mul: (x, y) => x * y,
      div: (x, y) => division(x, y)
    }
  })

  function calcular() {
    const {num_01, num_02, filter} = estado;
    estado.result = estado.operations[filter](parseFloat(num_01), parseFloat(num_02));
  }

</script>

<template>
  <div class="container">
    <label for="nb1">N. 01: </label>
    <input v-model="estado.num_01" @input="calcular" type="number" class="entrance" name="nb1"> <br />

    <div class="operations">
      <select v-model="estado.filter" @change="calcular">
        <option value="sum">➕</option>
        <option value="sub">➖</option>
        <option value="mul">✖️</option>
        <option value="div">➗</option>
      </select>
    </div>

    <label for="nb2">N. 02: </label>
    <input v-model="estado.num_02" @input="calcular" type="number" class="entrance" name="nb2">
    <br />
    <br />
    <!-- RESULTADO: -->
    <label for="result" style="font-weight: 500;">Result:</label>
    <input type="text" name="result" id="result" :value="estado.result">
  </div>

</template>

<style scoped>
  .container {
    max-width: 320px;
    margin: 0 auto;
    padding: 30px;
    background-color: aliceblue;
  }

  .entrance {
    margin-top: 15px;
    margin-bottom: 10px;
  }

  .operations {
    width: 100%;
    display: block;
    text-align: center;
    /* margin: 100 auto; */
  }

  label {
    color: black;
    margin-right: 5px;
  }

  #result {
    background-color: rgb(234, 236, 137);
  }

</style>
