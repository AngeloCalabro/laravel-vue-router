<template>
    <section>
        <h1>Lista dei project</h1>
        <div class="row">
            <div class="col-12 col-md-4" v-for="(project, index) in projects" :key="index">
                <div class="card" style="width: 18rem;">
                    <div class="h-75">
                        <img :src="`${store.imagBasePath}${project.cover_image}`" class="card-img-top w-100" :alt="project.title" v-if="(project.cover_image)">
                        <img src="https://via.placeholder.com/100x100.png?text=Placeholder" class="card-img-top w-100" :alt="project.title" v-else>
                    </div>
                    <div class="card-body">
                        <h5 class="card-title">{{ project.name_project }}</h5>
                        <p class="card-text">{{ truncateContent(project.description)}}</p>
                        <router-link class="btn btn-primary" :to="{ name: 'single-project', params: { slug: project.slug } }">
                            Vedi il progetto
                        </router-link>
                    </div>
                </div>
            </div>
        </div>
        <nav aria-label="Page navigation example">
            <ul class="pagination">
                <li class="page-item">
                    <a class="page-link" @click="prev()" href="#">Previous</a>
                </li>
                <li class="page-item" v-for="n in lastPage">
                    <span class="page-link btn" @click="getProjects(n)">{{ n }}</span>
                </li>
                <li class="page-item">
                    <span class="page-link btn" @click="next()" href="#">Next</span>
                </li>
            </ul>
        </nav>
    </section>
</template>

<script>
import axios from 'axios';
import { store } from '../store';
    export default {
        name: 'ProjectList',
        data(){
            return{
                store,
                projects: [],
                currentPage: 1,
                i: 0,
                lastPage: null,
                total: 0,
                contentMaxLen: 100
            }
        },
        methods: {
            getProjects(pageNum){
                axios.get(`${this.store.apiBaseUrl}/projects`, {params:{page: pageNum}}).then((response)=>{
                    this.projects = response.data.results.data;
                    this.currentPage = response.data.results.current_page;
                    this.lastPage = response.data.results.last_page;
                    this.total = response.data.results.total;
                })
            },
            prev(){
                if (this.currentPage > 1){
                    this.currentPage--;
                    this.getProjects(this.currentPage)
                }
            },
            next(){
                if (this.currentPage < this.lastPage) {
                    this.currentPage++;
                    this.getProjects(this.currentPage)
                }
            },
            truncateContent(text) {
                if (text.length > this.contentMaxLen) {
                    return text.substr(0, this.contentMaxLen) + '...';
                }
                return text;
            }
        },
        mounted(){
            this.getProjects(1);
        }
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