<script setup>
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'

function showMenu(){
  console.log('hellop');
}
</script>

<template>
  <header class="head">
    <div class="head__logoBox">
      <RouterLink to="/" class="head__logo">
        anto__dev
      </RouterLink>

    </div>



    <nav class="head__nav">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/projets">About</RouterLink>
    </nav>
    <button class="head__btn" @click="showMenu">
      <svg xmlns="http://www.w3.org/2000/svg" width="44" height="24" viewBox="0 0 44 24" fill="none">
        <rect width="44" height="4" rx="2" fill="#933FFF" />
        <rect y="10" width="12" height="4" rx="2" fill="#933FFF" />
        <rect x="32" y="10" width="12" height="4" rx="2" fill="#933FFF" />
        <rect y="20" width="44" height="4" rx="2" fill="#933FFF" />
      </svg>
    </button>
  </header>

  <RouterView />


</template>

<style scoped lang="scss">
.head {
  width:100vw;
  height: 60px;
  background-color: #fff;
  position: fixed;
  bottom: 0;
  left: 0;
  padding: 9px 3vw;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  border: 2px solid red;

  &__logoBox {
    display: flex;
    height: 100%;
    flex-direction: column;
    justify-content: center;
  }

  &__logo {
    color: #000;
    font-family: "kuga";
    font-size: 21px;
    font-weight: 400;
  }

  &__nav {
    opacity: 0;
    z-index: -1;
    position: relative;
  }

  &__btn {
    height: 24px;
    width: 44px;
background: transparent;
border: none;
  }

}
</style>
