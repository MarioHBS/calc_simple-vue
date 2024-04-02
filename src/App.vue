<script setup>
</script>

<template>
  <div class="container">
    <label for="nb1">N. 01: </label>
    <input type="number" class="entrance" name="nb1" id="nb1"> <br />

    <div class="operations">
      <select name="oper" id="">
        <option value="sum">➕</option>
        <option value="dif">➖</option>
        <option value="mul">✖️</option>
        <option value="div">➗</option>
      </select>
    </div>

    <label for="nb2">N. 02: </label>
    <input type="number" class="entrance" name="nb2" id="nb2">
    <br />
    <br />
    <label for="result">Result:</label>
    <input type="text" name="result" id="result">
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
    background-color: rgb(228, 121, 102);
  }

</style>
