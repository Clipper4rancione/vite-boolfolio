<script>



export default {
    name: "ProjectCard",
    props:{
        project: Object
    }
}
</script>

<template>
        <h2 class="proj_title">{{project.name}}</h2>
        <p class="proj_title">{{project.summary}}</p>
        <p class="proj_title">Category: {{project.summary}}</p>
</template>


<style lang="scss">
@use '../style/general'
  
</style>