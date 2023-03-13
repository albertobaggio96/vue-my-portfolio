<template>
  <header>
    <nav class="navbar navbar-expand-lg bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <router-link :to="{ name: 'home'}" class="nav-link">home</router-link> 
            </li>
            <li class="nav-item">
              <router-link :to="{ name: 'about'}" class="nav-link">about</router-link> 
            </li>
            <li class="nav-item">
              <router-link :to="{ name: 'projects'}" class="nav-link">projects</router-link> 
            </li>
            <li class="nav-item">
              <a class="nav-link disabled">Disabled</a>
            </li>
          </ul>
        </div>
          </div>
    </nav>
  </header>
</template>

<script>
  export default {
      
  }
</script>

<style lang="scss">
  
</style>