<script>
export default {
  name: 'ProjectCard',
  props: [
    'project',
    'show'
  ]
}
</script>

<template>
  <h1 v-if="show">
    {{ project.title }}
  </h1>

  <div class="position-relarive hidden-button">
    <figure :class="show ? 'card-show' : 'card-list'">
      <img v-if="project.preview.startsWith('img/')" :src="'http://127.0.0.1:8000/storage/' + project.preview"
        :alt="project.title" class="img-fluid">
      <img v-else :src="project.preview" :alt="project.title" class="img-fluid">
    </figure>
    <div v-if="!show" class="position-absolute bottom-0 start-50 translate-middle-x d-flex">
      <router-link :to="{ name: 'project', params: { slug: project.slug } }" class="btn btn-covered me-2 btn-single-card">
        <span class="span-mother">
          <span>S</span><span>h</span><span>o</span><span>w</span>
        </span>
        <span class="span-mother2">
          <span>S</span><span>h</span><span>o</span><span>w</span>
        </span>
      </router-link>
      <a :href="project.github" class="btn btn-covered btn-github">
        <span class="span-mother">
          <span>G</span><span>i</span><span>t</span><span>h</span><span>u</span><span>b</span>
        </span>
        <span class="span-mother2">
          <span>G</span><span>i</span><span>t</span><span>h</span><span>u</span><span>b</span>
        </span>
      </a>
    </div>
  </div>

  <article v-if="show">
    <h1>Author: {{ project.user.name }}</h1>
    <div>Date: {{ project.date }}</div>
    <div>Type: {{ project?.type?.type ?? 'unknown' }}</div>
    <div>Technologies: {{ project.slug }}
      <span v-if="project.technologies.length > 0" v-for="technology in project.technologies">{{ technology.technology + ''}}</span>
      <span v-else>unknown</span>
    </div>
  </article>
</template>

<style lang="scss" scoped>
  @use '../styles/partials/variables.scss' as *;
  div.hidden-button{
    figure.card-list{
      height: 230px;
      overflow: hidden;
      position: relative;
      bottom: 0;
      margin: 0;
      z-index: 1;
      transition: .7s;
      img{
        width: 100%;
      }
    }
    &:hover figure.card-list{
      bottom: 40px;
    }

    a.btn-covered {
    color: white;
    border-radius: 2rem;
    width: 100px;
    height: 35px;
    display: flex;
    justify-content: center;
    align-items: center;

    &.btn-single-card{
      background-color: $blue-nav;
    }
    &.btn-github{
      background-color: $black-git;
    }
    .span-mother {
      display: flex;
      overflow: hidden;
    }

    &:hover .span-mother {
      position: absolute;
    }

    &:hover .span-mother span {
      transform: translateY(1.2em);
    }

    .span-mother span:nth-child(1) {
      transition: .2s;
    }

    .span-mother span:nth-child(2) {
      transition: .3s;
    }

    .span-mother span:nth-child(3) {
      transition: .4s;
    }

    .span-mother span:nth-child(4) {
      transition: .5s;
    }

    .span-mother span:nth-child(5) {
      transition: .6s;
    }

    .span-mother span:nth-child(6) {
      transition: .7s;
    }

    .span-mother2 {
      display: flex;
      position: absolute;
      overflow: hidden;
    }

    .span-mother2 span {
      transform: translateY(-1.2em);
    }

    &:hover .span-mother2 span {
      transform: translateY(0);
    }

    .span-mother2 span {
      transition: .2s;
    }

    .span-mother2 span:nth-child(2) {
      transition: .3s;
    }

    .span-mother2 span:nth-child(3) {
      transition: .4s;
    }

    .span-mother2 span:nth-child(4) {
      transition: .5s;
    }

    .span-mother2 span:nth-child(5) {
      transition: .6s;
    }

    .span-mother2 span:nth-child(6) {
      transition: .7s;
    }
    }

  }
</style>