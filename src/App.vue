<script>

import axios from 'axios';

export default {
  name: 'App',
  data(){
    return{
      baseUrl: 'http://127.0.0.1:8000/api/'
    }
  },
  methods:{
    getApi(){
        axios.get(this.baseUrl + 'projects')
            .then(result => {
                this.projects = result.data.project_array;
            })
  

    },

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
          <h3 class="proj_title">{{project}}</h3>
        </div>
    </div>
  </div>
</template>

<style lang="scss">
@use './style/general'
</style>