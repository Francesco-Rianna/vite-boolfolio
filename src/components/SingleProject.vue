<script>
export default {
    name:'SinglePost',
    props : {
        projectData : Object
    }
}
</script>
<template>
        <div  class="card mb-3" style="width: 14rem;">
            <div class="card-body">
                <h5 class="card-title">{{projectData.name}}</h5>
                <h6 class="card-subtitle mb-2 text-body-secondary">{{projectData.client_name}}</h6>
                <p class="card-text">{{projectData.summary}}.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
            </div>
        </div>

</template>
<style scoped>
</style>