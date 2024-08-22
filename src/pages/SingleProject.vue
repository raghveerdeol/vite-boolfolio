<script>
import ProjectCard from '@/components/ProjectCard.vue';
import axios from 'axios';

export default {
data() {
return {
    project: {},
}
},
components:{
    ProjectCard
},
methods:{
    getProjects(id){
        axios.get(`http://127.0.0.1:8000/api/projects/${id}`, {
            params: {

            }
        })
        .then((response) => {
            console.log(response.data.results);
            this.project = response.data.results;
        })
        .catch(function (error){
            console.log(error);
        })
    }
},
created(){
    this.getProjects( this.$route.params.id);
}
}
</script>

<template>
            <ProjectCard  :title="project.title" :content="project.content" :language="project.language" :finished="project.finished" :image_url="project.image_url" :website="project.website_url" :technologies="project.technologies" :type="project.type" />
</template>

<style scoped>

</style>