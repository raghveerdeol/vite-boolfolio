<script>
import ProjectCard from './ProjectCard.vue';
import axios from 'axios';

export default {
components:{
    ProjectCard
},
data() {
return {
    projects: [],
}
},
props: {
    

},
methods:{
    getProjects(){
        axios.get('http://127.0.0.1:8000/api/projects', {
            params: {

            }
        })
        .then((response) => {
            console.log(response.data.results.data);
            this.projects = response.data.results.data;
        })
        .catch(function (error){
            console.log(error);
        })
    }
},
created(){
    this.getProjects();
}
}

</script>

<template>
    <router-link v-for="project in projects" :to="{name: 'single-project', params: { id: project.id}}" class="text-decoration-none">
        <ProjectCard  :title="project.title" :content="project.content" :language="project.language" :finished="project.finished" :image_url="project.image_url" :website="project.website_url" :technologies="project.technologies" :type="project.type" />
    </router-link>
</template>

<style scoped>

</style>