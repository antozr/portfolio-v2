<script setup>
import { ref } from 'vue'
import BoxTitleHome from '../components/BoxTitleHome.vue';
import InterBoxTitleVue from '../components/InterBoxTitleVue.vue';
import ContactSection from '../components/ContactSectionVue.vue';
import CardProjectSet from '../components/CardProjectSet.vue';
import RowCard from '../components/RowCard.vue';
</script>

<script>
let nbTag = ref(20);


let sizeScreen = screen.width;
let cardSize = document.querySelector('.cardProjet');
console.log(cardSize);


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

        <InterBoxTitleVue :title1="'Tout voir'"  :withText="true" :WithLink="false" :id-tag="'projets'" />

    <section class="sect__projetBox">

            <div class="projetBox__navTag" >
                <ul class="navTag__list">
                    <li class="navTag__el"  name="hello">
                        bonjour tag
                    </li>
                    <li class="navTag__el navTag__el--count"  id="nbTagCount" :ref="nbTag">
                        +{{ nbTag }}
                    </li>
                </ul>
                
            </div>
            <div class="projetBox__listCardB">
              <RowCard :visible2="true"/>
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
    margin: 0 ;
    

  }
&__projetBox{
  width: 100%;
  background-color: #FDF8E9;
  border-bottom: 2px solid red;
  padding: 0 3.4vw;
}
}
.hoeroBan__firstB{
    width:100%;
}
.sect__contactBox{
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
      width:calc(100% + 1.5vw);
      height: 130vh;
      //border: 2px solid greenyellow;
      margin: 0 0 0 -1.5vw;
      padding: 10vh 1.5vw 15vh 3.5vw;
    }

  }
}
</style>