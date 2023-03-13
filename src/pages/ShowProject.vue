<template >
  <main>
    <section class="row">
      <article class="card mb-3 col-12">
        <ProjectCard :project="project" />
      </article>
    </section>
  </main>
</template>

<script>

import axios from 'axios';

import ProjectCard from '../components/ProjectCard.vue';

export default {
  name: 'ShowProject',
  components: {
    ProjectCard,
  },
  data() {
    return {
      projectsUrl: `http://127.0.0.1:8000/api/projects`,
      project: '',
      slug: this.$route.params.slug

    }
  },
  methods: {
    getProjectsApi() {
      axios.get(`${this.projectsUrl}/${this.slug}`)
        .then((response) => {
          console.log(response.data)
          this.project = response.data.results
        })
        .catch(function (error) {
          console.log(error);
        })
    },
  },
  created() {
    this.getProjectsApi()
  }
}

</script>
<style lang="">
  
</style>