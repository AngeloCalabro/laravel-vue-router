<template>
    <section>
        <h1>Lista dei project</h1>
        <div class="row">
            <div class="col-12 col-md-4" v-for="(project, index) in projects" :key="index">
                <CardComponent :project="project"></CardComponent>
            </div>
        </div>
        <nav aria-label="Page navigation example">
            <ul class="pagination">
                <li class="page-item" :class="{'disabled': currentPage === 1}">
                    <button class="page-link" :disabled="currentPage === 1" @click="getProjects(currentPage - 1)">Previous
                    </button>
                </li>
                <li class="page-item" v-for="n in lastPage">
                    <span class="page-link btn" @click="getProjects(n)">{{ n }}</span>
                </li>
                <li class="page-item" :class="{'disabled': currentPage === lastPage}">
                    <button class="page-link" :disabled="currentPage === lastPage" @click="getProjects(currentPage + 1)">Next
                    </button>
                </li>
            </ul>
        </nav>
    </section>
</template>

<script>
import axios from 'axios';
import CardComponent from '../components/CardComponent.vue';
import { store } from '../store';
    export default {
    name: "ProjectList",
    data() {
        return {
            store,
            projects: [],
            currentPage: 1,
            i: 0,
            lastPage: null,
            total: 0,
        };
    },
    methods: {
        getProjects(pageNum) {
            axios.get(`${this.store.apiBaseUrl}/projects`, { params: { page: pageNum } }).then((response) => {
                this.projects = response.data.results.data;
                this.currentPage = response.data.results.current_page;
                this.lastPage = response.data.results.last_page;
                this.total = response.data.results.total;
            });
        },
        // prev() {
        //     if (this.currentPage > 1) {
        //         this.currentPage--;
        //         this.getProjects(this.currentPage);
        //     }
        // },
        // next() {
        //     if (this.currentPage < this.lastPage) {
        //         this.currentPage++;
        //         this.getProjects(this.currentPage);
        //     }
        // },
    },
    mounted() {
        this.getProjects(1);
    },
    components: { CardComponent }
}
</script>

<style lang="scss" scoped>
.card{
    width: 300px;
    height: 500px;
    text-align: center;
    margin: 1rem;
}

</style>