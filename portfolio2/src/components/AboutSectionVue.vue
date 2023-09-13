<script setup>
import SmallColInfoVue from "./SmallColInfo.vue";
import BoxTitleHome from './BoxTitleHome.vue';
import { ref } from "vue";

let allLinkAbout = [{name: 'Design',actif:true}, {name: 'Frontend', actif: false}, {name:'Logiciel?', actif: false},{name:'+ sur moi', actif: false}];
let arrayAbout = [{
    title1 : "Conception d'interface",
    allItem : [
        "je suis",
        "tu es","tu es",'nius'
    ]
},{
    title1 : "Conception de contenus graphiques",
    allItem : [
        "nous suis",
        "tu es","tu es",'nius'
    ]
}]

const itemData = ref(0)
console.log(itemData.value);
function updateItemList(e){
  if(e.target.innerText === "Design"){
    itemData.value = 1
  }else{
    itemData.value = 0
  }
}
</script>


<template>
    <div class="sect__about">
  <div class="sect__topAbout">
<div class="sect__boxSmallLLink"  :style="{background: '#ffffff'}">
    <IconLongBoxStar />
    <div class="boxSLLink__boxNav">
      <ul class="boxSLLink__list">
        
        <li class="boxSLLink__el" v-for="(item, index) in allLinkAbout" :key="index" v-on:click="updateItemList">
          
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
<div class="topAbout__mainCont">
  <ul class="topAbout__listFirst">
    <li class="topAbout__elFirst">
      <h3 class="sect__title  sect__txt--bigW">
        Conception d'interfaces
      </h3>
      <ul class="topAbout__listItem">
        <li class="topAbout__elI" v-for="(item, index) in arrayAbout[itemData].allItem" :key="index">
            {{item}} - {{ index }}
        </li>
      </ul>
    </li>

    <li class="topAbout__elFirst">
      <h3 class="sect__title  sect__txt--bigW">
        Conception d'interfaces
      </h3>
      <ul class="topAbout__listItem">
        <li class="topAbout__elI">
         -  je suis
        </li>
        <li class="topAbout__elI">
          je suis
        </li>
        <li class="topAbout__elI">
          je suis
        </li>
        <li class="topAbout__elI">
          je suis
        </li>
      </ul>
    </li>
  </ul>
</div>
  </div>
  <div class="sect__botAbout">
    <BoxTitleHome :title1="'Des infos'" :title2="'en vrac'" :BigClass="'titleBBox__titleB--big'"/>
  </div>
</div>
</template>