<template>
  <div class="relative bg-gray-900 h-full">
    <img class="w-full h-full opacity-50 bg-gray-900 custom-blur" :src="photo" alt="">
    <div class="absolute top-0 left-0 w-full h-full flex flex-col justify-center items-center">
      <mobile-welcome-component v-if="this.$props.isMobile" :isMobile="this.$props.isMobile"></mobile-welcome-component>
      <regular-welcome-component v-else :isMobile="this.$props.isMobile"></regular-welcome-component>
    </div>
  </div>
</template>

<script>
import MobileWelcomeComponent from './MobileWelcomeComponent.vue';
import RegularWelcomeComponent from './RegularWelcomeComponent.vue';

export default {
  name: "MaskedImage",
  props: ["photo", "isMobile"],
  components: {
    RegularWelcomeComponent,
    MobileWelcomeComponent
  }
};
</script>

<style scoped>
.custom-blur {
  filter: blur(4px);
}
</style>