
<script setup>
import IconBoxStar from '../components/icons/IconBoxStar.vue';

const props = defineProps({
  WithLink: Boolean,
  title1: String,
  title2: String,
  withText: Boolean,
  idTag: String,
  colorBG: String
});

</script>
<template>
    <div class="sect__interTitreBox" :id="idTag" :class="colorBG" ref="{{idTag}}">
      <div class="interBox__mainB">
        <div class="interBox__boxDeco">
          <IconBoxStar></IconBoxStar>
        </div>
        
        <div class="interBox__txtBox" :class="[withText === false ? 'interBox__txtBox  interBox__txtBox--small' : 'interBox__txtBox ']">
          <h2 :class="[withText === false ? 'sect__title sect__title--3 sect__title--kuga' :'sect__title sect__title--big sect__title--kuga' ]">
          {{ title1 }}
          <a href="../assets/pdf/CV-Dumont-Antoni-fr-en.pdf" v-show="WithLink" download class="interBox__link">check moi</a>
        </h2>
        <p class="sect__txt sect__txt--thin" v-show="withText">
          {{ title2 }}
        </p>
        </div>
        <div class="interBox__boxDeco interBox__boxDeco--end">
          <IconBoxStar></IconBoxStar>
        </div>
        

      </div>
    </div>
</template>