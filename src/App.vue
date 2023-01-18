<template>
  <div>
    <h1>{{ title }}</h1>
    <ul>
      <li v-for="(project,id) in projects" :key="id">
        {{ project.name_project }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',
  data() {
    return {
      title: 'Hi Vue!',
      apiURL: 'http://localhost:8000/api',
      projects: [],
    }
  },
  methods: {
    getProject() {
      axios.get(`${this.apiURL}/projects`).then((response) => {
        // console.log(response)
        this.projects = response.data.results.data;
        console.log(this.projects);
        console.log(response.data);
      })
    }
  },
  mounted() {
    this.getProject();
  }
}
</script>

<style lang="scss" scoped>

</style>