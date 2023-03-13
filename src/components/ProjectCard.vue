<script>
export default {
  name: 'ProjectCard',
  props: [
    'project'
  ]
}
</script>

<template>
  <h1 class="card-header fs-4">
    {{ project.title }}
  </h1>
  <div class="card-body">
    <img v-if="project.preview.startsWith('img/')" :src="'http://127.0.0.1:8000/storage/' + project.preview"
      :alt="project.title" class="img-fluid">
    <img v-else :src="project.preview" :alt="project.title" class="img-fluid">
    <p class="card-title">Author: {{ project.user.name }}</p>
    <p class="card-text">Date: {{ project.date }}</p>
    <p class="card-text">Type: {{ project?.type?.type ?? 'unknown' }}</p>
    <p class="card-text">Technologies: {{ project.slug }}
      <span v-if="project.technologies.length > 0" v-for="technology in project.technologies">{{ technology.technology + ''}}</span>
      <span v-else>unknown</span>
    </p>
  </div>
</template>

<style lang="scss"></style>