<script setup>
import { ref } from 'vue'

const props = defineProps({
 urlImg: String,
 titlePr : String,
 description: String,
 tagss: Array,
 smallCard : String
})
</script>





<template>
  <div class="cardProjet" :class="smallCard">
    <div class="cardProjet__imgBox">
      <img src="#" class="cardProjet__img" alt="" />
    </div>

    <div class="cardProjet__boxContent">
      <h2 class="cardProjet__title cardProjet__title--2">
        Noprojetm du {{ titlePr }} 
      </h2>
      <p class="cardProjet__txt">
        Travail de fin d’études sur la création d’un storytelling avec l’aide de react & framer.
      </p>
      <div class="cardProjet__tagBox">
        <svg xmlns="http://www.w3.org/2000/svg" width="25" height="14" viewBox="0 0 25 14" fill="none">
          <path fill-rule="evenodd" clip-rule="evenodd"
            d="M12.2381 0C11.6188 4.60244 10.9316 6.03656 5.38462 6.8535C6.0782 7.22499 6.71031 7.48914 7.28958 7.73121C9.35218 8.59314 10.7449 9.17512 11.8574 13.3262C14.4709 8.54776 16.0863 7.74006 18.7109 6.47275C14.7401 6.66314 13.2225 4.16656 12.2381 0ZM3 1.79543e-05C1.34315 1.79543e-05 0 1.34316 0 3.00002V11C0 12.6569 1.34315 14 3 14H21.2308C22.8876 14 24.2308 12.6569 24.2308 11V3.00002C24.2308 1.34316 22.8876 1.79543e-05 21.2308 1.79543e-05L12.2381 0L3 1.79543e-05Z"
            fill="black" />
        </svg>
        <ul class="cardProjet__tagList">
          <li class="cardProjet__tag">
            <p class="cardProjet__tagTxt">
              TAGGG {{ tagss }}
            </p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.cardProjet {
  max-width: 467px;
  width: calc(100% / 3);
  min-width: 200px;
  height: auto;
  &--small{
    width: 360px;
    margin: 0 10px;
  }

}

.cardProjet__imgBox {
  border-radius: 17px;
  background: #000;
  height: 293px;
  width: calc(100% - 16px);
  margin: 0 8px;
}

.cardProjet__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.cardProjet__boxContent {
  border-radius: 15px;
  background: #FFDBA1;
  min-height: 120px;
  padding: 21px 21px 18px;
  display: flex;
  flex-direction: column;
  row-gap: 16px;
  margin: -96px 0 0 0;
}

.cardProjet__tagBox{
  margin: 16px 0 0 0;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: end;
  width: 100%;
  height: 28px;

}
.cardProjet__tagList {

  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  column-gap: 16px;

   width: 100%;
   height: 100%;
}
.cardProjet__tag {
  border-radius: 20px;
  border: 1px solid #000;
  background: #FFF;
  padding: 7px 21px;
  display: flex;
  align-items: center;
}


</style>