
  
  <script setup>
  import {ref, onMounted} from 'vue';

  let chart = null;
  
  const dataset = [
	300, 50, 100
  ]
const data = {
  labels: [
    'Red',
    'Blue',
    'Yellow'
  ],
  datasets: [{
    label: 'My First Dataset',
    data: [300, 50, 100],
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
	const ctx = document.getElementById('chart');
	chart = new Chart (ctx, config);
})

  </script>
  
  <template>
	<div>
  <canvas id="chart"></canvas>
</div>
  </template>


  <style scoped>
  </style>
  