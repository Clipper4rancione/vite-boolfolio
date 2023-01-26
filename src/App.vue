<script>
import axios from 'axios';
import ProjectCard from './components/ProjectCard.vue';
export default {
    name: "App",
    components:{
      ProjectCard
    },
    data(){
        return{
            baseUrl: 'http://127.0.0.1:8000/api/'
        }
    },
    methods: {
        getApi(){

            axios.get(this.baseUrl + 'projects')
            .then(result => {
                this.projects = result.data.project_array;
                console.log(this.projects);
            })
            
        }
    },
    mounted(){
        this.getApi();
        
    }
}
</script>

<template>
    <div class="main-wrapper">
    <div class="container">
        <h1>Elenco Progetti CM</h1>
        <div class="proj_box" v-for="project in projects" :key="project.id">
          <h2 class="proj_title">{{project.name}}</h2>
          <p class="proj_title">{{project.summary}}</p>
          <p class="proj_title">Category: {{project.summary}}</p>
        </div>
    </div>
  </div>
</template>

<style lang="scss">
@use './style/general'
</style>