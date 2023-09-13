<script setup>
import SmallColInfoVue from "./SmallColInfo.vue";
import BoxTitleHome from './BoxTitleHome.vue';
import IconStarWhite1 from './icons/IconStarWhite1.vue';
import { ref } from "vue";

let allLinkAbout = [{ name: 'Design', actif: true }, { name: 'Frontend', actif: false }, { name: 'Logiciel?', actif: false }, { name: '+ sur moi', actif: false }];
let arrayAbout = [
  {
    title1: "Conception d'interface",
    title2: "Conception de contenus graphiques",
    allItem1: [
      "Wireframes",
      "Design",
      "Atomic design",
      "Responsive design",
      "Respect UX & UI",
      "..."
    ], allItem2: [
      "Icône / illustration SVG",
      "Modifications d'images sur PS",
      "Création d'images sur PS",
      "Écriture de contenus"
    ]
  }, {
    title1: "Intégration pure",
    title2: "Web app",
    allItem1: [
      "Intégration page web",
      "SEO",
      "Utilisation CMS",
      "Du simple au complexe",
      "..."
    ], allItem2: [
      "Création d'app web",
      "Utilisation de frameWork",
      "Vue / React / Svelte ...",
      "Atomic components",
      "..."
    ]
  }, {
    title1: "Des logiciels comme ...",
    title2: "Des langages",
    allItem1: [
      "La suite adobe",
      "Figma",
      "Visual Studio Code ",
      "Android Studio",
      "..."
    ], allItem2: [
      "Js vanilla",
      "React / Next / Vue / Svelte ",
      "Php",
      "Python & Kotlin en débutant",
      "..."
    ]
  }, {
    title1: "Mes passions",
    title2: "Des langages",
    allItem1: [
      "La musique & le piano",
      "L'art & les illustrations",
      "Les animaux & la nature ",
      "Les jeux vidéos",
      "..."
    ], allItem2: [
      "Créatif",
      "Passionné  ",
      "Persévérant",
      "Toujours prêt à apprendre",
      "..."
    ]
  }]

const itemData = ref(0)
console.log(itemData.value);
function updateItemList(e) {
  if (e.target.innerText === allLinkAbout[0].name) {
    itemData.value = 0
  } else if (e.target.innerText === allLinkAbout[1].name) {
    itemData.value = 1
  } else if (e.target.innerText === allLinkAbout[2].name) {
    itemData.value = 2
  } else if (e.target.innerText === allLinkAbout[3].name) {
    itemData.value = 3
  }
  else {
    itemData.value = 0
  }
};

function changeStateElNav(e) {
 let allLinkek = document.querySelectorAll('.boxSLLink--allEL')
 allLinkek.forEach((el)=>{
      el.classList.remove('boxSLLink__el--actif');
      
    });
    console.log(e);
  if (e.target.classList == 'boxSLLink--allEL') {
   
    e.target.classList.add('boxSLLink__el--actif');
    
  }
}
</script>


<template>
  <div class="sect__about">
    <div class="sect__topAbout">
      <div class="sect__boxSmallLLink" :style="{ background: '#ffffff' }">
        <IconStarWhite1 :class="'topAbout__starYellow'" />
        <div class="boxSLLink__boxNav">
          <ul class="boxSLLink__list">

            <li class="boxSLLink__el" v-for="(item, index) in allLinkAbout" :key="index" v-on:click="updateItemList">

              <p :class="[item.actif ? ' boxSLLink__el--actif boxSLLink--allEL ' : 'boxSLLink--allEL']" v-on:click="changeStateElNav">
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
      <div class="topAbout__mainCont">
        <ul class="topAbout__listFirst">
          <li class="topAbout__elFirst">
            <h3 class="sect__title  sect__txt--bigW">
              {{ arrayAbout[itemData].title1 }}
            </h3>
            <ul class="topAbout__listItem">
              <li class="topAbout__elI" v-for="(item, index) in arrayAbout[itemData].allItem1" :key="index">
                - {{ item }}
              </li>
            </ul>
          </li>

          <li class="topAbout__elFirst">
            <h3 class="sect__title  sect__txt--bigW">
              {{ arrayAbout[itemData].title2 }}
            </h3>
            <ul class="topAbout__listItem">
              <li class="topAbout__elI" v-for="(item, index) in arrayAbout[itemData].allItem2" :key="index">
                - {{ item }}
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
    <div class="sect__botAbout">
      <BoxTitleHome :title1="'Des infos'" :title2="'en vrac'" :BigClass="'titleBBox__titleB--big'" />
    </div>
  </div>
</template>