<template>
  <Carousel :autoplay="4000" :wrap-around="true">
    <Slide v-for="(item, index) in items" :key="index">
      <div class="carousel_item">
        <img :src="item.image" :alt="item.title" class="carousel-image" />
      </div>
    </Slide>
    <template #addons>
      <Pagination />
    </template>
  </Carousel>
  <div class="gallery">
    <div class="gallery_item" v-for="img in galleryImages" :key="img">
      <img :src="img" class="gallery_image" />
    </div>
  </div>
</template>

<script setup>
import { Carousel, Pagination, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

import defile1 from '../assets/basket1.png'
import defile2 from '../assets/foot1.png'
import defile3 from '../assets/galerie.png'
import galerie2 from '../assets/galerie2.png'
import galerie3 from '../assets/galerie3.png'
import galerie4 from '../assets/galerie4.png'
import galerie5 from '../assets/galerie5.png'
import galerie6 from '../assets/galerie6.jpg'
import galerie7 from '../assets/galerie7.png'


const items = [
  { image: defile1 },
  { image: defile2 },
  { image: defile3 }
]

const galleryImages = [galerie2, galerie3, galerie4, galerie5, galerie6, galerie7]
</script>

<style scoped>
.carousel_item {
  display: flex;
  color: white;
  text-align: center;
}

.carousel-image {
  width: 100%;
  border-radius: 0px;
}

.gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap:10px;
  margin: 5%;
}

.gallery_item {
  width: 32%; 
  margin-bottom: 20px;
}

.gallery_image {
  width: 100%;
  border-radius: 8px;
}

@media (max-width: 668px) {

 .gallery_item{
  width:100%
 }
}

</style>
