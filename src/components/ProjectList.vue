<script>
import axios from 'axios';
export default {
    name :'ProjectList',
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
        <div v-for="project in projects" class="card mb-3" style="width: 14rem;">
            <div class="card-body">
                <h5 class="card-title">{{project.name}}</h5>
                <h6 class="card-subtitle mb-2 text-body-secondary">{{project.client_name}}</h6>
                <p class="card-text">{{project.summary}}.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
            </div>
        </div>
    </div>
</template>

<style scoped>
</style>