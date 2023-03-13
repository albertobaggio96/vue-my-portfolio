<template>
  <main>
    <section class="row">
      <div class="col-12 py-3 d-flex justify-content-between">
        <button @click="prevPage()" class="btn btn-primary ms-5" :class="currentPage === 1 ? 'disabled' : ''">prev</button>
        <button @click="nextPage()" class="btn btn-primary me-5" :class="currentPage === lastPage ? 'disabled' : ''">next</button>
      </div>

      <article class="card mb-3 col-4" v-for="project in projects">
        <ProjectCard :project="project" />
        <router-link :to="{ name: 'project', params: { slug: project.slug } }">Show</router-link>
      </article>
    </section>
  </main>
</template>


<script>
import axios from 'axios';

import ProjectCard from '../components/ProjectCard.vue';

export default {
  name: 'mainApp',
  components: {
    ProjectCard,
  },
  data() {
    return {
      projectsUrl: 'http://127.0.0.1:8000/api/projects',
      projects: '',
      currentPage: 1,
      lastPage: ''
    }
  },
  methods: {
    getProjectsApi() {
      axios.get(this.projectsUrl, {
        params: {
          page: this.currentPage
        }
      })
        .then((response) => {
          console.log(response.data.results.data)
          this.projects = response.data.results.data
          this.lastPage = response.data.results.last_page
        })
        .catch(function (error) {
          console.log(error);
        })
    },
    nextPage() {
      if (this.currentPage < this.lastPage) {
        this.currentPage++
        console.log(this.currentPage)
        this.getProjectsApi()
      }
    },
    prevPage() {
      if (this.currentPage > 1) {
        this.currentPage--
        console.log(this.currentPage)
        this.getProjectsApi()
      }
    },

  },
  created() {
    this.getProjectsApi()
  }
}
</script>


<style></style>