<template>
  <div>
    <div id="">
      <h1 class="display-1">
        <span><img id="logo" src="./assets/logo.png"></span>
        Thomas J. Hu
      </h1>
    </div>

    <p id="subtitle" class="lead text-muted">Aspiring Software Engineer</p>
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
</style>
