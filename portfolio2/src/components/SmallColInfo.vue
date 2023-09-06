<script setup>
import IconLongBoxStar from './icons/IconLongBoxStar.vue';
import { RouterLink } from 'vue-router'
import IconRoundStar from '../components/icons/IconRoundStar1.vue';


const props = defineProps({
  WithLink: Boolean,
  title2: String
});

let allLinkProject = [{name: 'TFE',actif:true}, {name: 'Archeo', actif: false}, {name:'Frontmentor', actif: false}];


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

  <div class="sect__boxSmallLLink" v-show="WithLink == false">
    <IconLongBoxStar />
    <div class="boxSLLink__boxNav">
      <ul class="boxSLLink__list">
        <li class="boxSLLink__el" v-for="item in allLinkProject" v-bind="key">
          
          <p  :class="[item.actif ? ' boxSLLink__el--actif ' : '']">
            {{ item.name}}
          </p>
        </li>
      </ul>

      <RouterLink to="/projets" class="boxSLLink__linkBtn">

        Tous voir
      </RouterLink>

    </div>
    <div class="boxSLLink__boxDec1">
          <IconRoundStar />
        </div>
  </div>
</template>