<template>
  <div id="app">
      <!-- navbar -->
      <div class="navbar navbar-expand-lg fixed-top navbar-dark" style="background-color: #42b983">
        <div class="container">
        <router-link to="/" class="navbar-brand">Página Inicial</router-link>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarResponsive">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a href="https://drive.google.com/open?id=1cZy3ySYNzudELlKK35yIyONN_cA90h2C" target="_blank" class="nav-link">Atividade 1</a>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/contact">Contato</router-link>
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
