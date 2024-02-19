<script setup>
import { ref } from 'vue';
import { routeLocationKey, RouterLink, RouterView, routerViewLocationKey } from 'vue-router'
import IconMail1 from './components/icons/IconMail1.vue';
// import HelloWorld from './components/HelloWorld.vue'

function showMenu() {
  console.log('hellop');
}

let dataNav1 = [];
//console.log(window.location.hash)


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
  changeNavdata()

}
function scrollHomeToAnchorPoint(refName, itemELLink) {
  scrollToAnchorPoint(refName, itemELLink);
  dataNav1 = ["Mon travail", "+ D'infos", "Contact"];
  //changeNavdata();
}



function changeNavdata() {

  if (window.location.hash === '#/') {

    dataNav1 = ["Mon travail", "+ D'infos", "Contact"];

  } else {
    dataNav1 = ["Mes projets", "D.graf", "Contact"]
  }
}

changeNavdata();

function goSpoti() {
  window.open('https://open.spotify.com/playlist/5gRvtuRYpTcVNCAca8346Z?si=a3245445b6b44578', '_blank')
};

function goProjectPage(refName, itemELLink) {
  //console.log(window.location.hash)
  scrollToAnchorPoint(refName, itemELLink);
  changeNavdata();
 // console.log(dataNav1);
  dataNav1 = ["Mes projets", "D.graf", "Contact"];
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
      <RouterLink to="/" @click="scrollHomeToAnchorPoint('/', 0)" class="head__link head__link--actif">Home</RouterLink>
      <!-- {# <RouterLink to="/projets" class="head__link">About</RouterLink> #} -->
      <RouterLink to="/projets" @click="goProjectPage('/', 1)" class="head__link">Tous&nbsp;mes&nbsp;projets</RouterLink>
      <a @click="scrollToAnchorPoint('#projets', 2)" class="head__link">{{ dataNav1[0] }}</a>

      <a @click="scrollToAnchorPoint('#infos', 3)" class="head__link">{{ dataNav1[1] }}</a>
      <a @click="scrollToAnchorPoint('#contact', 4)" class="head__link">{{ dataNav1[2] }}</a>
    </nav>
    <div class="head__spotyBut" @click="goSpoti()">
      <svg width="38" height="38" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd">
        <path fill="#9D77BF"
          d="M19.098 10.638c-3.868-2.297-10.248-2.508-13.941-1.387-.593.18-1.22-.155-1.399-.748-.18-.593.154-1.22.748-1.4 4.239-1.287 11.285-1.038 15.738 1.605.533.317.708 1.005.392 1.538-.316.533-1.005.709-1.538.392zm-.126 3.403c-.272.44-.847.578-1.287.308-3.225-1.982-8.142-2.557-11.958-1.399-.494.15-1.017-.129-1.167-.623-.149-.495.13-1.016.624-1.167 4.358-1.322 9.776-.682 13.48 1.595.44.27.578.847.308 1.286zm-1.469 3.267c-.215.354-.676.465-1.028.249-2.818-1.722-6.365-2.111-10.542-1.157-.402.092-.803-.16-.895-.562-.092-.403.159-.804.562-.896 4.571-1.045 8.492-.595 11.655 1.338.353.215.464.676.248 1.028zm-5.503-17.308c-6.627 0-12 5.373-12 12 0 6.628 5.373 12 12 12 6.628 0 12-5.372 12-12 0-6.627-5.372-12-12-12z" />
      </svg>
    </div>
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

  &__spotyBut {
    width: 38px;
    height: 38px;
    cursor: pointer;
    padding: 6px 0 0 0;

    &>svg {
      width: 100%;
      height: 100%;
      scale: 1.2;
    }

    &:hover {
      transition: 0.3s;
      opacity: 0.8;
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

}
</style>
