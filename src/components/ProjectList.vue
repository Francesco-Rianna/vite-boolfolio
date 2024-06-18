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
          currentPage:1,
          prevPageUrl:null,
          nextPageUrl:null,
          projects:[]
         };
    
    },
    methods :{
     getProjects(pageNumber){
       axios.get('http://127.0.0.1:8000/api/projects',{
          params : {
            page: pageNumber
          }
       })
       .then((response)=>{
        this.projects=response.data.results.data;
        this.currentPage = response.data.results.current_page
        this.prevPageUrl = response.data.results.prev_page_url
        this.nextPageUrl = response.data.results.next_page_url
       });
     }
    },
    mounted() {
     this.getProjects(this.currentPage)

    }
    
}
</script>

<template>
    <div class="container d-flex flex-wrap gap-2">
       <SingleProject v-for="project in projects" :projectData="project"></SingleProject>

    </div>
    <div class="container">
        <nav aria-label="Page navigation example">
            <ul class="pagination">
                <li class="page-item" v-if="prevPageUrl"><button class="page-link cursor-pointer" @click="getProjects(currentPage - 1 )">Previous</button></li>
                <li class="page-item" v-if="nextPageUrl"><button class="page-link cursor-pointer"  @click="getProjects(currentPage + 1 )">Next</button></li>
            </ul>
        </nav>
    </div>
</template>

<style scoped>
</style>