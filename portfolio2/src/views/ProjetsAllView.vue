<script setup>
import { ref } from 'vue'
import BoxTitleHome from '../components/BoxTitleHome.vue';
import InterBoxTitleVue from '../components/InterBoxTitleVue.vue';
import ContactSection from '../components/ContactSectionVue.vue';
import CardProjectSet from '../components/CardProjectSet.vue';
import SmallColInfo from '../components/SmallColInfo.vue';
import IconLongBoxStar from '../components/icons/StarYellow.vue'
import RowCard from '../components/RowCard.vue';
</script>

<script>
let nbTag = ref(20);


let sizeScreen = screen.width;
let cardSize = document.querySelector('.cardProjet');
console.log(cardSize);
let allLinkAbout = [
  {
    "name": "p.Scolaire",
    "actif": false,
  },
  {
    "name": "p.Personnel",
    "actif": false,
  },
  {
    "name": "p.Defis",
    "actif": false,
  },
  {
    "name": "p.Jeux & app",
    "actif": false,
  },
  {
    "name": "p.Random ?",
    "actif": false,
  },
  {
    "name": "Tous voir",
    "actif": true,
  },

]

</script>
<template>
  <main>
    <div class="sect__hoeroBan">
      <div class="hoeroBan__firstB">
        <div class="hoeroBan__textBox1">
          <h2 class="sect__title sect__title--2">
            Soit Curieux 👀!
          </h2>
          <p class="sect__txt">
            Viens voir mes différents projets !<br>
            Il y en a pour tout les gouts, alors vas les découvrir.<br>
            <b>Tu vas bien t’amuser.</b> <br>
            Tu trouveras peut-être une pépite !
          </p>


        </div>
        <BoxTitleHome :title1="'Projet'" :title2="'en vrac !'" />
      </div>


    </div>

    <InterBoxTitleVue :title1="'Tout voir'" :withText="true" :WithLink="false" :id-tag="'projets'" />

    <section class="sect__projetBox">
      <div class="projetBox__colGN">
        <div class="sect__boxSmallLLink projetBox__smallLink">
        <IconLongBoxStar />
        <div class="boxSLLink__boxNav">
          <ul class="boxSLLink__list">
            <li class="boxSLLink__el" v-for="(item, index) in allLinkAbout" :key="index" v-on:click="updateItemList">

              <p :class="[item.actif ? ' boxSLLink__el--actif boxSLLink--allEL ' : 'boxSLLink--allEL']"
                v-on:click="changeStateElNav">
                {{ item.name }}
              </p>
            </li>
          </ul>

          <RouterLink to="/projets" class="boxSLLink__linkBtn" v-show="WithBtn">

            Tous voir
          </RouterLink>

        </div>
        <div class="boxSLLink__boxDec1">
          <IconRoundStar />
        </div>
      </div>
      </div>
      <div class="projetBox__contentIm">
        <div class="projetBox__navTag">
          <ul class="navTag__list">
            <li class="navTag__el" name="hello">
              bonjour tag
            </li>
            <li class="navTag__el navTag__el--count" id="nbTagCount" :ref="nbTag">
              +{{ nbTag }}
            </li>
          </ul>

        </div>
        <div class="projetBox__listCardB">
          <RowCard :visible2="true" />
        </div>
      </div>
    </section>

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
    background: #FDF8E9;
    margin: 0;


  }

  &__projetBox {
    width: 100%;
    background-color: #FDF8E9;
    border-bottom: 2px solid red;
    padding: 0 3.4vw 0 2.5vw ;
    display: flex;
    flex-direction: row;
    justify-content: space-between;

  }
}

.hoeroBan__firstB {
  width: 100%;
}

.sect__contactBox {
  margin: 0;
}

@media(min-width:900px) {
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
}</style>