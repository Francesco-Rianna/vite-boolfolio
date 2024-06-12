<script>
import axios from 'axios';
import SingleProject from './SingleProject.vue';
export default {
    name :'ProjectList',
    components: {
        SingleProject
    },
    data(){
         return{
          projects:[]
         };
    
    },
    methods :{
     getProjects(){
       axios.get('http://127.0.0.1:8000/api/projects')
       .then((response)=>{
        this.projects=response.data.results;
        console.log(this.projects)
       });
     }
    },
    mounted() {
     this.getProjects()
    }
    
}
</script>

<template>
    <div class="container d-flex flex-wrap gap-2">
       <SingleProject v-for="project in projects" :projectData="project"></SingleProject>
    </div>
</template>

<style scoped>
</style>