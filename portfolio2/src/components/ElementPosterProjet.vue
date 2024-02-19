<script setup>
import PageProjetDs from '../components/PageDescriptionProjet.vue';
import { ref } from 'vue'


const props = defineProps({
    reverseStyle : Boolean,
    title : String,
    titleSpan : String,
    description : String,
    srcImg : String
})




</script>
<script>
//let visibleOver = ref(false);
// function openOverlay(){
//   console.log('hellelel');
//  visibleOver= ref(true);
//  console.log(visibleOver.value);
// }
function aniRevOut(el){
  
  console.log(this);
}
</script>

<template>
 
  <li class="projetGraf__imgBoxEl" :class="[reverseStyle ?'projetGraf__imgBoxEl--reverse':'']"  >
              <div class="projetGraf__imgSub" :class="[reverseStyle ?'projetGraf__imgSub--reverse':'']" @mouseout="aniRevOut()" >
                <img
                  :src="srcImg"
                  alt="Voici une poster représentant une BMW M1, créer par antoni dumont. "
                  class="projetGraf__img"
                  :class="[reverseStyle ?'projetGraf__img--reverse':'']"
                />
              </div>
              <div class="projetGraf__boxTxt">
                <h3 class="sect__title sect__title--small3">
                  {{ title }}
                  <span class="sect__title--kuga projetGraf__txtColor">{{ titleSpan }} </span>
                </h3>
                <p class="sect__txt">
                  {{ description }}
                </p>
              </div>
          
            
          </li>
         
          
</template>