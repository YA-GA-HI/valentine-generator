<template>
<div class="d-flex flex flex-column align-items-center justify justify-content-between app ">

<!--top bar-->
<nav class="container-fluid py-3 bg-primary">
<h3>Valentine Generator</h3>
</nav>

<!--app-->

<div class="zenku-container card text-center">

  <div class="card-body">
      <h2 class="card-title">Enter a name now!</h2>

      <div class="mt-3">
        <input type="text" class="form-control text-center" placeholder="I love ...">
      </div>

      <button href="#" class="btn btn-lg mt-3 bg-primary text-light">Go somewhere</button>

  </div>
</div>

<!--footer-->
<footer>
<a href="#">

</a>
<a href="#"></a>
<a href="#"></a>
</footer>
</div>
</template>

<script>
export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
*{
outline: 1px solid red;
}
#app , .app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  height: 100vh;
  width: 100vw !important;
  overflow: hidden;
}

.bg-primary{
  background-image: linear-gradient(90deg, rgb(252, 61, 81), rgb(255, 129, 62));
}

.zenku-container{
width: 800px;}
</style>
