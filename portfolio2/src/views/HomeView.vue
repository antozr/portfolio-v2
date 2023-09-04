<script setup>
import BoxTitleHome from '../components/BoxTitleHome.vue';
import IconStarWhite1 from '../components/icons/IconStarWhite1.vue';
import IconRoundStar from '../components/icons/IconRoundStar1.vue';
</script>

<template>
  
  
    <div class="sect__hoeroBan">
      <div class="hoeroBan__firstB">
        <div class="hoeroBan__textBox1">
          <h2 class="sect__title sect__title--2">
            Hey!
          </h2>
          <p class="sect__txt">
            Bienvenus ici 👋. <br />
            Moi c’est Antoni, <b>un designer / Front-end dev junior</b>, qui touche à tous, pour faire des expériences
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
        <ul class="hoeroBan__listTxt1">
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

        <div class="hoeroBan__boxDec1">
          <IconRoundStar />
        </div>
      </div>

      <div id="projets">
        jesuis projet
      </div>

    </div>


  
</template>

<style lang="scss" scoped>


.sect {

  &__hoeroBan {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    column-gap: 21px;
    border: 2px solid red;
    width: 100%;
  // background: blue;

  }

}
@media(min-width:900px){
  .sect {

&__hoeroBan {

  flex-wrap: nowrap;

}

}
}
</style>

