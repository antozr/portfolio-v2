<script setup>
import BoxTitleHome from '../components/BoxTitleHome.vue';
import IconStarWhite1 from '../components/icons/IconStarWhite1.vue';
import IconRoundStar from '../components/icons/IconRoundStar1.vue';
import IconBoxStar from '../components/icons/IconBoxStar.vue';
import InterBoxTitleVue from '../components/InterBoxTitleVue.vue';
import SmallColInfoVue from '../components/SmallColInfo.vue';
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

        <SmallColInfoVue :WithLink="true" />

        <div class="hoeroBan__boxDec1">
          <IconRoundStar />
        </div>
      </div>



    </div>
    <InterBoxTitleVue />
    <div class="sect__project">

      <SmallColInfoVue :WithLink="false" />
      <div class="sect__projetBoxImg">
        <div class="projetBI__containtImg">
          <div class="projetBI__imgBox">
            <img
              src="https://images.unsplash.com/photo-1692936002249-2f0c5e2390c4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80"
              alt="This is in screenshot of my project." class="projetBI__img" loading="lazy">
          </div>
        </div>

        <div class="projetBI__boxTitleI">
          <h2 class="sect__title--kuga sect__title sect__title--2">
            TFE : TattooExplore
          </h2>
          <ul class="projetBI__listTagT">
            <li class="projetBI__elTag sect__txt">
              Scolaire
            </li>
            <li class="projetBI__elTag sect__txt">
              2023
            </li>
          </ul>
        </div>

      </div>
      <div class="sect__projectDes">
        <div class="projectDes__boxT">
          <p class="sect__txt sect__txt--bigW">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Magnam facilis dolores pariatur labore quia numquam
            ipsa. Ullam ab magni in?
          </p>
          <br/>
          <p class="sect__txt">
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Amet quam numquam eum voluptatem explicabo? Velit
            reprehenderit perferendis iure ut blanditiis ullam, adipisci repellat! Magnam eos beatae tempore rerum ipsa,
            autem voluptate veniam, assumenda ut et totam, sapiente rem repellat possimus.
          </p>
        </div>
        <a href="#" class="projectDes__link">
          Voir le projet
        </a>
      </div>
    </div>
  </main>
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

  &__project {
    display: flex;
    flex-direction: column;

  }

}

@media(min-width:900px) {
  .sect {

    &__hoeroBan {

      flex-wrap: nowrap;

    }

    &__project {
      flex-direction: row;
      height: 90vh;
      border: 2px solid greenyellow;

    }

  }
}
</style>

