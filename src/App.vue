<script setup>
import ImageCarousel from './components/ImageCarousel.vue';
import ChatPart from './components/ChatPart.vue';
</script>
<template>
  <div class="container mx-auto px-4">
    <div class="flex items-center justify-center h-screen">
          <div class="image-carousel">
              <ImageCarousel/>
          </div>
    </div>
    <div class="flex items-center justify-center h-screen mt-10">
          <div class="cart">
              <ChatPart/>
          </div>
    </div>

</div>
</template>
<style>
.cart{
  width: 400px;
  height: 400px;
  background-color: rgb(202, 142, 195);
}
</style>
