<script setup>
import BoxTitleHome from '../components/BoxTitleHome.vue';
import IconStarWhite1 from '../components/icons/IconStarWhite1.vue';
import IconRoundStar from '../components/icons/IconRoundStar1.vue';
import InterBoxTitleVue from '../components/InterBoxTitleVue.vue';
import SmallColInfoVue from '../components/SmallColInfo.vue';
import ProjectGlobalVue from '../components/ProjectGlobalVue.vue';
import ABoutSectionVue from '../components/AboutSectionVue.vue';
import ContactSection from '../components/ContactSectionVue.vue';
</script>


<script>

function scrollTop(){
  window.scrollTo({
      top: 0,
      left: 0,
      behavior: 'smooth'
    })
}

</script>
<template>
  <main>
    <div class="sect__hoeroBan">
      <div class="hoeroBan__firstB">
        <div class="hoeroBan__textBox1">
          <h2 class="sect__title sect__title--2">
            Hey!
          </h2>
          <p class="sect__txt">
            Bienvenus ici 👋. <br />
            Moi c’est Antoni, <b>un designer / Front-end dev junior</b>, qui touche à tout, pour faire des expériences
            uniques et agréables.
          </p>
          <p class="sect__txt">
            J’apporte ma vision & créativité là où il en faut & je réalise mes projets en respectant les exigences
            demandée.
          </p>

        </div>
        <BoxTitleHome :title1="'Antoni aka'" :title2="'anto__dev'" />
      </div>

      <div class="hoeroBan__secondB">
        <div class="hoeroBan__boxDec2">
          <IconStarWhite1 />
        </div>

        <SmallColInfoVue :WithLink="true" />

        <div class="hoeroBan__boxDec1">
          <IconRoundStar />
        </div>
      </div>



    </div>
    <InterBoxTitleVue :title1="'Des Projets'" :title2="'Scolaires -/- personnels -/- des défis -/- & bien d’autres'" :withText="true" :WithLink="false" :id-tag="'projets'"/>
    <ProjectGlobalVue/>
   
    <router-link to="/projets" @click="scrollTop()" class="sect__linkPrBigBox">

      <BoxTitleHome :title1="'Tout'+' découvrir'" :title2="'*soit curieux'"  :BigName="true"/>
    </router-link>
    <InterBoxTitleVue :withText="false" :WithLink="true" :title1="'Un CV,'" :idTag="'+infos'" :colorBG="'sect__interTitreBox--white'"/>
    <div id="infos"></div>
<ABoutSectionVue />
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
    background: #FDF8E9;
    margin: 0 ;
    

  }

  &__linkPrBigBox{

    &>.sect__titleBBox{
        background: #933FFF;
        &::before{
          transition: 0.6s;
          transform: translateY(80%) translateX(30%) scaleX(0.8) skewX(15deg);
          background-image: url(../assets/images/poster-giulletta-spider-affiche-insta.webp);
          object-fit: cover;
          opacity: 0.8;
          aspect-ratio:9 / 12;
          width: 100%;
          height: 60%;
          
        }
    }
    &:hover{
      &>.sect__titleBBox{
        background: #933FFF;
        transition: 0.3s;

        &::before{
          transition: 0.6s;
          //transform: translateY(30%) translateX(30%) scaleX(0.8) skewX(15deg);
          //background-image: url(../assets/images/poster-giulletta-spider-affiche-insta.webp);
          opacity: 0.8;
          aspect-ratio:9 / 12;
          width: 40%;
          animation:moveBoxImgHover 1.8s  both;
        }
      }
    }
  }

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
      height: 110vh;
      //border: 2px solid greenyellow;
      margin: 0 0 0 -1.5vw;
      padding: 10vh 1.5vw 3vh 3.5vw;
    }

    &__linkPrBigBox{
      &>.sect__titleBBox{
      background: #1d1d1d;
        &::before{
          transition: 0.6s;
          transform: translateY(0%) translateX(0%) scaleX(1) skewX(0deg);
          background-image: url(../assets/images/degradation-box-title-min.webp);

          width: 100%;
          height: 100%;
          
        }
      }

    }
  }
}

/* animation */

@keyframes moveBoxImgHover {
  from{
    width: 100%;
    height: 100%;
    opacity: 1;
  }
  10%{
    scale: 0.5;
    opacity: 0;
  }
  50%{
    transform: scale(1) scaleX(0.8) translateX(60%);
    background-image: url(../assets/images/poster-giulletta-spider-affiche-insta.webp);
    opacity: 0.6;
  }
  80%{
    transform: scale(1)  translateY(25%) translateX(40%) scaleX(0.8) skewX(5deg);
    opacity: 0.9;
  }

  to{
    transform: translateY(30%) translateX(30%) scaleX(0.8) skewX(15deg);
    background-image: url(../assets/images/poster-giulletta-spider-affiche-insta.webp);
    opacity: 0.9;

  }

}
</style>

