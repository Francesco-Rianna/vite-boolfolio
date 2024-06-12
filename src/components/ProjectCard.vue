<script>
import axios from 'axios';
export default {
    name :'ProjectCard',
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
    <div class="container">
        <div v-for="project in projects" class="card" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <h6 class="card-subtitle mb-2 text-body-secondary">Card subtitle</h6>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
            </div>
        </div>
    </div>
</template>

<style scoped>
</style>