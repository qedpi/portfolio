<template>
  <div>
    <div class="jumbotron jumbotron-fluid bg-success text-white">
      <h1 class="display-1">
        <!--<span><img id="logo" src="./assets/logo.png"></span>-->
        Thomas J Hu
      </h1>
      <p id="subtitle" class="lead">Aspiring Software Engineer &nbsp;
        <a href="https://github.com/qedpi/" target="_blank">
          <i class="fa fa-github"></i>
        </a> &nbsp;
        <a href="https://www.linkedin.com/in/qedpi" target="_blank">
          <i class="fa fa-linkedin"></i>
        </a>
      </p>
    </div>
    <hr>
  </div>
</template>

<script>
  export default {
    name: "portfolio-header"
  }
</script>

<style scoped>
  #subtitle {
    font-size: 26px;
  }

  #logo {
    height: 100px;
    margin-bottom: 20px;
  }

  .jumbotron {
    padding: 1rem;
    margin-bottom: -1rem;
    background-color: white;
  }

  #subtitle i{
    color: white;
  }
</style>
