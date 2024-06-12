<script>
import ProjectCard from './components/ProjectCard.vue';
import AppHeader from './components/AppHeader.vue'


export default{
  components : {
    ProjectCard,
    AppHeader
  }

}
</script>

<template>
  <header>
    <AppHeader></AppHeader>
  </header>
  <main>
    <ProjectCard> </ProjectCard>
  </main>

</template>

<style>
</style>
