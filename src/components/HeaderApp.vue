<template>
  <header>
    <nav class="navbar navbar-expand-lg navbar-dark">
      <div class="container d-flex">
        <figure class="rounded-circle mb-0 me-3">
          <img src="../assets/img/profile-picture.png" alt="AB"> 
        </figure>
        <router-link :to="{ name: 'about'}" class="navbar-brand">
          Alberto Baggio
        </router-link> 
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <router-link :to="{ name: 'home'}" class="nav-link">home</router-link> 
            </li>
            <li class="nav-item">
              <router-link :to="{ name: 'projects'}" class="nav-link">projects</router-link> 
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

<style lang="scss" scoped>
 @use '../styles/partials/variables.scss' as *;
  
  nav{
    background-color: $blue-nav;
    color: white;
    figure{
      width: 56px;
      height: 56px;
      overflow: hidden;
      img{
        width: 100%;
      }
    }
  }
</style>