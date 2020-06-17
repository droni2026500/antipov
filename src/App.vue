@import url('https://fonts.googleapis.com/css?family=Roboto+Condensed');
<template>
  <div id="app">
    <!-- navbar -->
      <div class="navbar navbar-expand-lg fixed-top navbar-dark bg-primary">
        <div class="container">
        <router-link to="/" class="navbar-brand">Главная страница</router-link>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarResponsive">
          <ul class="navbar-nav">
            <li class="nav-item">
              <router-link class="nav-link" to="/shopping">Покупки</router-link>
            </li>
          </ul>
        </div>
        </div>
      </div>
      <div class="container">
       <transition name="moveInUp">
         <router-view/>
       </transition>
        
      </div>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-family: 'Roboto Condensed', sans-serif;
}
.body{
  background: black;
}
.moveInUp-enter-active{
  animation: fadeIn 2s ease-in;
}
@keyframes fadeIn{
  0%{
    opacity: 0;
  }
  50%{
    opacity: 0.5;
  }
  100%{
    opacity: 1;
  }
}

.moveInUp-leave-active{
  animation: moveInUp .3s ease-in;
}
@keyframes moveInUp{
 0%{
  transform: translateY(0);
 }
  100%{
  transform: translateY(-400px);
 }
}
</style>

