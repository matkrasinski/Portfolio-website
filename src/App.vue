<template>
    <div class="bg-gradient-to-br from-slate-50 via-gray-300 to-slate-200">

      <default-navbar v-if="true"> </default-navbar>
      <welcome-component v-if="true"></welcome-component>
      <career-path v-if="true"></career-path>
      
      <projects-list v-if="true" class="mb-8"></projects-list>
      
      <skills-section v-if="true"></skills-section>
      
      <contact-form></contact-form>
    </div>
</template>

<script>
import DefaultNavbar from './components/layout/DefaultNavbar.vue';
import ProjectsList from './components/ProjectsList.vue';
import WelcomeComponent from './components/WelcomeComponent.vue'
import CareerPath from './components/CareerPath.vue';
import ContactForm from './components/ContactForm.vue';
import SkillsSection from './components/SkillsSection.vue';


export default {
  name: 'App',
  components: {
    DefaultNavbar,  
    ProjectsList,
    WelcomeComponent,
    CareerPath,
    ContactForm,
    SkillsSection
  }
}
</script>

<style scoped>
.container {
  flex: 1;
}

* {
    font-family: 'Inter', sans-serif;
  }


</style>