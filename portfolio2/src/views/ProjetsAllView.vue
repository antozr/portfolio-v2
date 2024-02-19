<script setup>
import { ref , onMounted} from 'vue'
import BoxTitleHome from '../components/BoxTitleHome.vue'
import InterBoxTitleVue from '../components/InterBoxTitleVue.vue'
import ContactSection from '../components/ContactSectionVue.vue'
import CardProjectSet from '../components/CardProjectSet.vue'
import SmallColInfo from '../components/SmallColInfo.vue'
import IconLongBoxStar from '../components/icons/StarYellow.vue'
import IconBoxStar from '../components/icons/IconBoxStar.vue'
import ELProjetPoster from '../components/ElementPosterProjet.vue'
import RowCard from '../components/RowCard.vue'
import dataProjets from '../assets/data/data-Projets.json'
import PageProjetDs from '../components/PageDescriptionProjet.vue'

/// gsap import 
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { ScrollToPlugin } from "gsap/ScrollToPlugin";


</script>

<script>
let nbTag = ref(20)

console.table(dataProjets)
let cardSize = document.querySelector('.cardProjet')
console.log(cardSize)
let allLinkAbout = [
  {
    name: 'p.Scolaire',
    actif: false
  },
  {
    name: 'p.Personnel',
    actif: false
  },
  {
    name: 'p.Defis',
    actif: false
  },
  {
    name: 'p.Jeux & app',
    actif: false
  },
  {
    name: 'p.Random ?',
    actif: false
  },
  {
    name: 'Tous voir',
    actif: true
  }
];

function scrollTop1(){
  window.scrollTo({
  top: 100,
  left: 0,
  behavior: "smooth",
});
}

/// code gsap
console.log(gsap.version);
gsap.registerPlugin(ScrollTrigger);
let ctx;
let main = ref();
onMounted(()=>{
  ctx = gsap.context((self) => {
    const boxes = self.selector('.sect__projetBox');
    boxes.forEach((box) => {
      gsap.to(box, {
        x: 150,
        scale:10,
        marker:true,
        scrollTrigger: {
          trigger: box,
          start: 'bottom bottom',
          end: 'top 20%',
          scrub: true,
        },
      });
    });
  }, main.value); // <- Scope!
})
</script>
<template>
  <main>
    <div class="sect__hoeroBan">
      <div class="hoeroBan__firstB">
        <div class="hoeroBan__textBox1">
          <h2 class="sect__title sect__title--2">Soit Curieux 👀!</h2>
          <p class="sect__txt">
            Viens voir mes différents projets !<br />
            Il y en a pour tout les gouts, alors vas les découvrir.<br />
            <b>Tu vas bien t’amuser.</b> <br />
            Tu trouveras peut-être une pépite !
          </p>
        </div>
        <BoxTitleHome :title1="'Projet'" :title2="'en vrac !'" />
      </div>
    </div>

    <section class="sect__projetBox">
      <div class="projetBox__colGN">
        <div class="sect__boxSmallLLink projetBox__smallLink">
          <IconLongBoxStar />
          <div class="boxSLLink__boxNav">
            <ul class="boxSLLink__list">
              <li class="boxSLLink__el boxSLLink__el--noHover" v-for="(item, index) in allLinkAbout" :key="index" v-on:click="updateItemList">
                <p :class="[
                  item.actif ? ' boxSLLink__el--actif boxSLLink--allEL ' : 'boxSLLink--allEL'
                ]" v-on:click="changeStateElNav">
                  {{ item.name }}
                </p>
              </li>
            </ul>

            <RouterLink to="/projets" class="boxSLLink__linkBtn" v-show="WithBtn" aria-label="Va vous rediriger vers la page des projets.">
              Tous voir
            </RouterLink>
          </div>
          <div class="boxSLLink__boxDec1">
            <IconRoundStar />
          </div>
        </div>
      </div>
      <div class="projetBox__contentIm" id="projets">
        <!-- <div class="projetBox__navTag">
          <ul class="navTag__list">
            <li class="navTag__el" name="hello">bonjour tag</li>
            <li class="navTag__el navTag__el--count" id="nbTagCount" :ref="nbTag">+{{ nbTag }}</li>
          </ul>
        </div> -->
        <div class="projetBox__listCardB" >
          <RowCard :visible2="true" />
        </div>
      </div>
    </section>
    
    <div class="sect__projetGraf" id="infos">
      <BoxTitleHome :title1="'Des projets'" :title2="'graphiques'" :BigClass="'titleBBox__titleB--big'" />
      <div class="projetGraf__section" >
        <ul class="projetGraf__rowImgBox">
          <ELProjetPoster :reverseStyle="false" :srcImg="'https://antoni-dumont.be/projets/portfolio/img/poster-m1-insta-d1630e31.jpg'"
            :title="'BMW' + '&nbsp;' + 'M' + '&nbsp;&nbsp;' + 'Poster'" :titleSpan="'expérience'" />

          <ELProjetPoster :reverseStyle="true" :srcImg="'https://antoni-dumont.be/projets/portfolio/img/igor_Blyat_11-040a14f5.webp'" :title="'Igor Blyat' + '&nbsp;' + 'the '"
            :titleSpan="'nuke' + '&nbsp;' + 'boy'" />
          <ELProjetPoster :reverseStyle="false" :srcImg="'https://antoni-dumont.be/projets/portfolio/img/poster-giulletta-spider-affiche-insta-6a4c618b.webp'" :title="'Alfa' + '&nbsp;' + 'Romeo,'"
            :titleSpan="'Milano'" />
        </ul>
        <div class="projetGraf__seeAll">
          <a href="https://www.instagram.com/zombirev/" class="projetGraf__linkBox">
            <div class="projetGraf__boxSeeMore">
              <div class="projetGraf__boxDecor">
                <IconBoxStar></IconBoxStar>
              </div>
              <p class="sect__txt sect__title--kuga">
                + de création (insta)
              </p>
            </div>
          </a>
        </div>
      </div>
    </div>
    <InterBoxTitleVue :with-text="true" :-with-link="false" :title1="'Un contact'" :id-tag="'contact'" :colorBG="'sect__interTitreBox--posHaute'" />
    <ContactSection />
  </main>
</template>

<style lang="scss" scoped>
.sect {
  &__hoeroBan {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    column-gap: 21px;
    //border: 2px solid red;
    width: 100%;
    // background: blue;
    padding: 0 3.4vw;
  }

  &__project {
    display: flex;
    flex-direction: column;
    width: 100vw;
    min-height: 40vh;
    background: #fdf8e9;
    margin: 0;
  }

  &__projetBox {
    width: 100%;
    background-color: #fdf8e9;
    //border-bottom: 2px solid red;
    padding: 4vh 3.4vw 0 2.5vw;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    border-radius: 60px 60px 0 0;
    margin: -40px 0 0 0;
    position: relative;
    z-index: 2;
  }
}

.hoeroBan__firstB {
  width: 100%;
}

.sect__contactBox {
  margin: 0;
}

@media (min-width: 900px) {
  .sect {
    &__hoeroBan {
      flex-wrap: nowrap;
      padding: 0 1.5vw;
    }

    &__project {
      flex-direction: row;
      width: calc(100% + 1.5vw);
      height: 130vh;
      //border: 2px solid greenyellow;
      margin: 0 0 0 -1.5vw;
      padding: 10vh 1.5vw 15vh 3.5vw;
    }
  }
}
</style>
