<script>
import ProjectList from './components/ProjectList.vue';
import AppHeader from './components/AppHeader.vue'


export default{
  components : {
    ProjectList,
    AppHeader
  }

}
</script>

<template>
  <header>
    <AppHeader></AppHeader>
  </header>
  <main>
    <ProjectList> </ProjectList>
  </main>

</template>

<style>
</style>
