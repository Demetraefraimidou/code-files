@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@600&family=Work+Sans:wght@500&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Darker+Grotesque:wght@700&display=swap');
<template>
  <div id="app">
    <head>
      <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
    </head>
    <Header/>
    <router-view id="content"/>
  </div>
</template>

<script>
import Header from './views/Header.vue'
  export default {
     components:{
         Header
     }
  }
</script>

<style>

#app {
  background-image: url("./assets/gradient.png");
  background-color: white;
  min-height: 100vh;
  background-attachment: fixed;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  font-size: 9px;
  display: inline-block;
  height: 100%;
  width: 100%;
}
.home{
  font-size: 5rem;
}

#title {
  font-family: 'Darker Grotesque', sans-serif;
  font-weight: bold;
  font-size: 8rem;
  width: 100%;
  color: black;
  padding-top: 2%;
}

#body {
  font-family: 'Space Grotesk', sans-serif;
  font-size: 10pt;
  color: black;
}

#nav {
  border: 3px solid black;
  position: fixed;
  font-family: 'Space Grotesk',sans-serif;
  color:white;
  font-size: 30px;
  width: 100%;
}

@media only screen and (max-width: 900px) {
  #content {
    position: fixed;
  }
}

#content {
  justify-content: space-around;
  font-size: 15px;
}

#nav a {
  color: #06213d;
}

#nav a.router-link-exact-active {
  color: #122896;
/*  width: 60%;*/
}

.margin-left {
  margin-left: 5%;
  float: right;
}
</style>
