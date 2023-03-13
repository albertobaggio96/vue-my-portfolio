<template>
  <section>
    <article class="row align-items-center h-100">
      <div class="offset-lg-3 col-lg-6 text-center p-5 rounded-5">
        <h1 class="mb-2">
          WELCOME! I'm Alberto,
        </h1> 
        <p>this is my website where you can find some of my projects and see the evolution of my skills.</p>
        <p>If you like you can see some of this by clicking the button below</p>
        <router-link :to="{ name: 'projects'}" class="btn btn-project"><font-awesome-icon icon="fa-solid fa-eye" class="fa-eye" /></router-link> 
      </div>
    </article>

  </section>
</template>

<script>
</script>

<style lang="scss" scoped>
  section{
    height: calc(100vh - 56px);
    background: #3482d0 ;

    article{
      background: url(../assets/img/circuit.png);
      color: white;
      font-size: 1.1rem;
    }

    div{
      box-shadow: 0px 0px 100px 100px #3482d0 ;
      background-color: #3482d0f9;
      animation: entrance 2s ease;  
    
    }
    .btn-project{
      color: #FFF;
      transition: all 0.5s;
      position: relative;
      height: 50px;
      width: 140px;
      font-size: 1.2rem;

      &::before {
        content: 'Projects';
        line-height: 50px;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        border-radius: 50px;

        background-color: #064199;
        transition: all 0.3s;
      }
      &:hover::before {
        opacity: 0 ;
        transform: scale(0.5,0.5);
      }
      &::after {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        opacity: 0;
        border-radius: 50px;
        background-color: #0a4fb7;
        transition: all 0.3s;
        transform: scale(0.5,0.5);
      }
      &:hover::after {
        opacity: 1;
        transform: scale(1,1);
      }
      .fa-eye{
        position: absolute;
        top: 50%;
        left: 50%;
        opacity: 0;
        transform: translate(-50%, -50%);
        color: white;
        font-size: 2rem;
      }
      &:hover .fa-eye{
        opacity: 1;
        z-index: 1;
        transition: .6s;
      }
    }
  }

    @keyframes entrance {
      0% {
        transform: translate(0px, -200px);
        opacity: 0;
      }
      100% {
        transform: translate(0px);
        opacity: 1;
      }
    } 
</style>
