<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <buttton @click="setData">버튼</buttton>
</template>

<script setup>
import {ref} from 'vue';

const data = ref('123123');

const setData = () => {
  data.value =  '버튼 눌렀음'
}

function sum(num) {
  let count = 0;
  for (let i = 0; i < num; i++) {
    count += 1;
    consoleFn(count);
  }

  return count;
}

function consoleFn(count) {
  console.log(`count: ${count}`);
  console.log("디버깅 테스트");
}

const result = sum(5);

console.log(result);

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
