<template>
    <div id="projectList" class="flex flex-col bg-gray-100 pt-32 shadow">
        <h1 class=" text-center text-6xl font-manrope font-black leading-snug text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 via-pink-600 to-purple-600">Projects</h1>
        
        <carousel :items-to-show="1" class="mb-32">
            
            <slide v-for="item in projectList" :key="item" class="h-full">
                <project-item :item="item"></project-item>
            </slide>
            
            <template #addons>
                <navigation />
            </template>
        </carousel>
    </div>
</template>

<script>
import ProjectItem from './ProjectItem.vue';
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Navigation } from 'vue3-carousel'

export default {
    name: 'CarouselProjectsList',
    props: ['projectList'],
    components: {
        Carousel,
        Slide,
        Navigation,
        ProjectItem
    },
}
</script>

<style scoped>
@media (max-width: 768px) {
  h1 {
    font-size: 2rem
  }
  p {
    font-size: 2rem
  }
}
</style>