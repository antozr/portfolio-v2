<script setup>
import IconLongBoxStar from './icons/IconLongBoxStar.vue';
import { RouterLink } from 'vue-router'
import IconRoundStar from '../components/icons/IconRoundStar1.vue';


const props = defineProps({
  WithLink: Boolean,
  title2: String,
  dataLink: String,
  WithBtn: Boolean,
  bgColor: String
});

let allLinkProject = [{name: 'TFE',actif:true}, {name: 'Archeo', actif: false}, {name:'CMG', actif: false}];
let allLinkAbout = [{name: 'Design',actif:true}, {name: 'Frontend', actif: false}, {name:'Logiciel?', actif: false},{name:'+ sur moi', actif: false}];

function addItemAbout(e){
  
  if(e.target.innerText === "Design"){
    localStorage.setItem('itemAbout',1)
  }else{
    localStorage.setItem('itemAbout',0)
  }
  
}
</script>


<template>
  <ul class="hoeroBan__listTxt1" v-show="WithLink">
    <li class="hoeroBan__elTxt1">
      <h3 class="sect__txt sect__title sect__title--smallF sect__txt--bigW">
        Designer
      </h3>
      <p class="sect__txt">
        UX / UI design<br />
        Responsive/ mobile<br />
        Web-designer
      </p>


    </li>
    <li class="hoeroBan__elTxt1">
      <h3 class="sect__txt sect__title sect__title--smallF sect__txt--bigW">
        Develloper
      </h3>
      <p class="sect__txt">
        Front-end<br />
        Web-app

      </p>


    </li>
  </ul>

  <div class="sect__boxSmallLLink" v-show="WithLink == false" :style="bgColor">
    <IconLongBoxStar />
    <div class="boxSLLink__boxNav">
      <ul class="boxSLLink__list">
        <li class="boxSLLink__el" v-for="item in allLinkProject" v-bind="key" v-show="dataLink === 'nameProject'" >
          
          <p  :class="[item.actif ? ' boxSLLink__el--actif ' : '']">
            {{ item.name}}
          </p>
        </li>
        <li class="boxSLLink__el" v-for="item in allLinkAbout" v-bind="key" v-show="dataLink === 'nameAbout'" v-on:click="addItemAbout">
          
          <p  :class="[item.actif ? ' boxSLLink__el--actif ' : '']">
            {{ item.name}}
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
</template>