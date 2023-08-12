<script setup>
import {ref, onMounted, onBeforeUnmount} from 'vue'
const images = ref([
  'https://images.unsplash.com/photo-1691215526536-d7fb13f3e0ff?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80',
  'https://images.unsplash.com/photo-1691168223030-5e5cadfe07d1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1032&q=80',
  'https://images.unsplash.com/photo-1691520673295-9626f624869b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80',
  'https://images.unsplash.com/photo-1691238450978-5abddc361f19?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDIxfDZzTVZqVExTa2VRfHxlbnwwfHx8fHw%3D&auto=format&fit=crop&w=500&q=60'
]);
let carousel = null

onMounted(()=>{
  carousel = new Flickity( '#makeCarousel')
})

onBeforeUnmount(() => {
	alert('The carousel component is about to be destroyed.');
  console.log('The carousel component is about to be destroyed.');
	if(carousel){
		carousel.destroy();
	}
});
</script>
<template>
		<h2 class="text-center">This is my Carousel</h2>
  <div class="items mx-auto" id="makeCarousel">
      <div class="item" v-for="(image, index) in images" :key="index" :style="`background-image:url(${image})`"></div>
  </div>
</template>
<style scoped>
.items{
  border: 2px solid rgb(193, 180, 180);
  height: 400px;
  width: 500px;
}
.item{
  height: 400px;
  width: 500px;
  background-size: cover;
  margin: 0 auto;
}
</style>