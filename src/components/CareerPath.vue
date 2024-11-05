<template>
  <div id="careerPath" class="my-16 lg:mx-64 mx-8">
    <h1 class="py-16 text-center text-6xl font-manrope font-black leading-snug text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 via-pink-600 to-purple-600">My Career Path</h1>
    <timeline-component class="rounded-3xl " v-if="true"></timeline-component>
  </div>
</template>

<script>
import TimelineComponent from "./TimelineComponent.vue";

export default {
  name: "CareerPath",
  components: {
    TimelineComponent,
  },
};
</script>

<style scoped>
.responsive-image {
  width: 100%;
  height: auto;
  min-width: 200px;
}

@media (min-width: 768px) {
  .responsive-image {
    max-width: 100%;
  }
}

@media (max-width: 768px) {
  h1 {
    font-size: 1.5rem;
  }
}

</style>
