<script>
  import HeaderApp from './components/HeaderApp.vue';
  // import MainApp from './components/MainApp.vue';

  export default{
    name:'App',
    components:{
      HeaderApp,
      // MainApp,
    }
  }
</script>

<template>
  <HeaderApp/>
  <router-view></router-view>
  <!-- <MainApp/> -->
</template>

<style lang="scss">
  @use './styles/general.scss'as *;
  @use 'bootstrap/scss/bootstrap.scss' as *;

  
</style>
