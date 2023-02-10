<template>
    <NavBar/>
    <InfoSection/>
    <SectionDivider/>
    <ProjectsSection/>
    <SectionDivider/>
    <InterestsSection/>
    <SectionDivider/>
    <GoalsSection/>
    <SectionDivider/>
    <FooterComp/>
</template>

<script>
import NavBar from './components/NavBar.vue'
import InfoSection from './components/InfoSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import SectionDivider from './components/SectionDivider.vue'
import InterestsSection from './components/InterestsSection.vue'
import GoalsSection from './components/GoalsSection.vue'
import FooterComp from './components/FooterComp.vue'

export default {
  name: 'App',
  components: {
    NavBar, 
    InfoSection,
    ProjectsSection,
    SectionDivider,
    InterestsSection,
    GoalsSection,
    FooterComp
  }

}
</script>

<style>
html {
  scroll-behavior: smooth;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
  margin-bottom: 0;
}
section {
  padding: 150px 80px 80px;
}

</style>
