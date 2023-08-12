<script setup>
import {ref, onMounted, onBeforeUnmount } from 'vue';

const newValue = ref(10);

let chart = null
const dataset =  [300, 50, 100]

const data = {
  labels: [
    'Red',
    'Blue',
    'Yellow'
  ],
  datasets: [{
    label: 'My First Dataset',
    data:dataset,
    backgroundColor: [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
      'rgb(255, 205, 86)'
    ],
    hoverOffset: 4
  }]
};

const config = {
  type: 'pie',
  data: data,
};

onMounted(()=>{
  const ctx = document.getElementById('pie_chart');
  chart = new Chart(ctx, config);

})

function update(){
    dataset.push(newValue.value);
    chart.data.datasets[0].data = dataset
    chart.update();
}

onBeforeUnmount (()=>{
  alert('Before clear all');
  chart.destroy();
})
</script>

<template>
  <div class="chart">
        <canvas id="pie_chart"></canvas>
        <div class="body">
          <input type="text" id="first_name" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" v-model="newValue">
          <button class="mt-2 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="update()">
            Button
          </button>
        </div>
  </div>
 
</template>



<style scoped>
.chart{
  width: 400px;
  height: 400px;
  background-color: rgb(202, 142, 195);
margin-top: 20px;
}
.chart_section{
  width: 400px;
  height: 200px;
  border: 1px solid black;
}

.body{
    width: 300px;
    height: 50px;
    margin: 30px auto;
}
</style>