<script setup>
import { RouterLink, RouterView } from 'vue-router'
import IconMail1 from './components/icons/IconMail1.vue';
// import HelloWorld from './components/HelloWorld.vue'

function showMenu() {
  console.log('hellop');
}
function scrollToAnchorPoint(refName, itemELLink) {
  let allHeadLink = document.querySelectorAll('.head__link');
  allHeadLink.forEach((el) => {
    el.classList.remove("head__link--actif")
  });
  
  if (refName === '/') {
    window.scrollTo({
      top: 0,
      left: 0,
      behavior: 'smooth'
    })
  } else {
    let el = document.querySelector(refName)

    el.scrollIntoView({ behavior: 'smooth' })
  }
  allHeadLink[itemELLink].classList.add('head__link--actif')
  // if(this.classList.contain == "head__link"){
  //   e.target.classList.add('head__link--actif')
  // }
  
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
      <RouterLink to="/" @click="scrollToAnchorPoint('/',0)" class="head__link head__link--actif">Home</RouterLink>
  <!-- {# <RouterLink to="/projets" class="head__link">About</RouterLink> #} -->
      <a @click="scrollToAnchorPoint('#projets',1)" class="head__link">Mon&nbsp;travail</a>
      <a @click="scrollToAnchorPoint('#infos',2)" class="head__link">+&nbsp;D'infos</a>
      <a @click="scrollToAnchorPoint('#contact',3)" class="head__link">Contact</a>
    </nav>
    <button class="head__btn" @click="showMenu">
      <svg xmlns="http://www.w3.org/2000/svg" width="44" height="24" viewBox="0 0 44 24" fill="none">
        <rect width="44" height="4" rx="2" fill="#933FFF" />
        <rect y="10" width="12" height="4" rx="2" fill="#933FFF" />
        <rect x="32" y="10" width="12" height="4" rx="2" fill="#933FFF" />
        <rect y="20" width="44" height="4" rx="2" fill="#933FFF" />
      </svg>
    </button>
    <a href="mailto:antonidwm@gmail.com" class="head__btnMail">
      Contact-moi
      <IconMail1 />
    </a>
  </header>

  <RouterView />
</template>

<style scoped lang="scss">
.head {
  width: 100vw;
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
  //border: 2px solid red;
  z-index: 40;

  &__logoBox {
    display: flex;
    height: 100%;
    width: 100%;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  &__logo {
    color: #000;
    font-family: "kuga";
    font-size: 21px;
    font-weight: 400;
  }

  &__nav {
    display: none;
    opacity: 0;
    z-index: -1;
    position: relative;
  }

  &__btn {
    height: 24px;
    width: 44px;
    background: transparent;
    border: none;
    display: none;
  }

  &__btnMail {
    display:
      none;
      color: #1d1d1d;
  }

  &__link {

    &--actif {
      color: var(--mauve, #9D77BF);

      font-family: "Neue-ut";
    }
  }

}

.rowGrid {
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
  display: flex;
  flex-direction: row;
  column-gap: 21px;
  padding: 0 21px;
  pointer-events: none;

  &>div {
    background: red;
    opacity: 0.1;
    height: 100%;
    width: calc((100% / 8) - 11px);
  }
}

@media(min-width:900px) {
  .rowGrid {

    column-gap: 28px;
    padding: 0 28px;

    &>div {
      width: calc((100% / 12) - 14px);
    }




  }

  .head {
    bottom: auto;
    left: 0;
    top: 0;
    width: calc(100% - 6vw);
    margin: 0 0 0 3vw;
    z-index: 30;
    padding: 9px 3vw;
    border: none;
    border-bottom: 2px solid #1d1d1d;

    &__logoBox {
    width: auto;
    align-items: flex-start;
  }
    &__btn {
      display: none;
    }

    &__btnMail {
      display: flex;
      flex-direction: row;
      font-family: 'Neue-reg';
      justify-content: space-evenly;
      align-items: center;
      text-align: center;
      font-family: "kuga";
      font-size: 18px;
      cursor: pointer;
      width: 191px;
      height: 47px;
      border-radius: 3px;
      background: #FFDBA1;
      border: none;
      transition: 0.3s;

      &:hover {
        transition: 0.6s;
        border: 1px solid #1d1d1d;
        background: #fff;


      }



    }

    &__nav {
      height: 38px;
      width: auto;
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: center;
      column-gap: 2vw;
      opacity: 1;
      z-index: 30;
      transform: translateY(50px);
      width: 60%;
      background: #fff;
      border-radius: 0 0 8px 8px;
      // border: 2px solid red;

    }

    &__link {
      color: #000;
      font-family: "neue-reg";
      font-size: 18px;
      font-weight: 400;

      &:hover {
        color: var(--mauve, #9D77BF);
        font-weight: 800;

      }

      &--actif {
        color: #9D77BF;

        font-family: "Neue-ut";
      }
    }
  }

}</style>
