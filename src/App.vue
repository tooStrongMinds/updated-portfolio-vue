<template>
  <div class="container">
    <NavBar />
    <Home />
    <Work />
    <About />
    <Footer />
  </div>
  

</template>

<script>
import NavBar  from './components/NavBar.vue'
import Home from './components/Home.vue'
import Work from './components/Work.vue'
import About from './components/About.vue'
import Footer from './components/Footer.vue'


export default {
  name: 'App',
  components: {
    NavBar, Home, Work, About, Footer
  }
}
</script>

<style>
#app {
  font-family: Work Sans, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #e3e4e6;
  /* color: #2c3e50;
  margin-top: 60px; */
  width: 90%;
  margin: 0 auto;
}
img {
  max-width: 100%;
}
h1 {
    font-weight: 100;
    font-size: 56px;
    line-height: 150%;
  }
h2 {
  font-weight: 100;
  font-size: 40px;
  line-height: 150%;
  text-align: left;
}
span {
  font-weight: 600;
}
@media (max-width: 900px) {
  h1 {
      font-size: 40px;
    }
    i {
      font-size: 25px;
    }
    h2 {
      width: 90%;
      font-size: 28px;
    }
}
</style>
