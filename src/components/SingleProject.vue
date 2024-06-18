<script>
export default {
    name:'SinglePost',
    props : {
        projectData : Object
    },
    methods : {
        truncateText(text) {
            if(text.length > 100) {
                return text.substr(0, 99) + '...';
            }

            return text;
        }

    }
}
</script>
<template>
        <div  class="card mb-3" style="width: 14rem;">
            <div class="card-body">
                <h5 class="card-title">{{projectData.name}}</h5>
                <h6 class="card-subtitle mb-2 text-body-secondary">{{projectData.client_name}}</h6>
                <div v-if="projectData.type" >
                    <div class="text-body-secondary"> Tecnologia utilizzata : {{ projectData.type.name }}</div>
                </div>
                <div v-else>
                    <div class="text-body-secondary"> Tecnologia utilizzata : nessuna</div>
                </div>
                <div>
                   <div > Tecnologia utilizzata :  <span v-for="technology in projectData.technologies"> {{ technology.name }},</span></div>
                </div>
                <p class="card-text">{{truncateText(projectData.summary)}}.</p>
                </div>
            </div>


</template>
<style scoped>
</style>