<template>
  <carousel :perPage='1'>
    <slide
      v-for="post in info" 
      :key="post.id"> 
      <a :href="post.id" :v-text="post.id">
        <img :src="post.image"/>
      </a>
    </slide>
  </carousel>
</template>

<script>
import { Carousel, Slide } from 'vue-carousel';

    export default {
        name: "ListaPost",
        props: {
            info: Array,
        },
        components: {
          Carousel,
          Slide
        }
    }
</script>