<template>
    <section v-if="project" class="text-center">
        <h1>{{ project.name_project }}</h1>
            <img :src="`${store.imagBasePath}${project.cover_image}`" class="card-img-top w-50" :alt="project.name_project" v-if="(project.cover_image)">
            <img src="https://via.placeholder.com/100x100.png?text=Placeholder" class="card-img-top w-50" :alt="project.title" v-else>
        <p>{{ project.description }}</p>
        <div v-if="project.category">
            <h5>Category: {{ project.category.name }}</h5>
        </div>
        <div v-if="project.languages && project.languages.length > 0">
            <h5>Linguaggio</h5>
            <div>
                <span v-for="(language, index) in project.languages" :key="index" class="badge text-bg-info">{{ language.name }}</span>
            </div>
        </div>
    </section>
    <section v-else>Loading...</section>
</template>

<script>
import axios from 'axios';
import { store } from '../store';
export default {
    name: 'SingleProject',
    data() {
        return {
            store,
            project: null,
        }
    },
    methods: {
        getProject() {
            console.log(this.$route);
            axios.get(`${this.store.apiBaseUrl}/projects/${this.$route.params.slug}`).then((response) => {
                //console.log(response.data.results);
                if (response.data.success) {
                    //console.log(response.data.results);
                    this.project = response.data.results;
                } else {
                    //console.log(this.$router);
                    this.$router.push({ name: 'not-found' });
                }
            });
        }
    },
    mounted() {
        this.getProject();
    }

}
</script>

<style lang="scss" scoped>

</style>