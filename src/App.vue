<template>
    <NavBar/>
    <InfoSection/>
    <SectionDivider/>
    <ProjectsSection/>
    <SectionDivider/>
    <div>
      There will be my interests listed
    </div>
    <SectionDivider/>
    <div>
      Section dedicated for my future goals
    </div>
    <SectionDivider/>
</template>

<script>
import NavBar from './components/NavBar.vue'
import InfoSection from './components/InfoSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import SectionDivider from './components/SectionDivider.vue'

export default {
  name: 'App',
  components: {
    NavBar, 
    InfoSection,
    ProjectsSection,
    SectionDivider
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
section {
  padding: 150px 80px 80px;
}

</style>
