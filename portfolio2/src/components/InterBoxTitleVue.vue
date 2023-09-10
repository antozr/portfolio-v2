
<script setup>
import IconBoxStar from '../components/icons/IconBoxStar.vue';

const props = defineProps({
  WithLink: Boolean,
  title1: String,
  withText: Boolean
});

</script>
<template>
    <div class="sect__interTitreBox" id="projets">
      <div class="interBox__mainB">
        <div class="interBox__boxDeco">
          <IconBoxStar></IconBoxStar>
        </div>
        
        <div class="interBox__txtBox" :class="[withText === false ? 'interBox__txtBox  interBox__txtBox--small' : 'interBox__txtBox ']">
          <h2 :class="[withText === false ? 'sect__title sect__title--3 sect__title--kuga' :'sect__title sect__title--big sect__title--kuga' ]">
          {{ title1 }}
          <a href="#" v-show="WithLink" download>mon CV</a>
        </h2>
        <p class="sect__txt sect__txt--thin" v-show="withText">
          Scolaires -/- personnelles -/- des défis -/- & bien d’autres
        </p>
        </div>
        <div class="interBox__boxDeco interBox__boxDeco--end">
          <IconBoxStar></IconBoxStar>
        </div>
        

      </div>
    </div>
</template>