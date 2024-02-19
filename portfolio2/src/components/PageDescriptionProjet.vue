<script setup>
import BoxTitleHome from '../components/InterBoxTitleVue.vue';

// window.scrollTo(0,0);
const props = defineProps({
    visibleB: Boolean,
    title1: String
})

</script>

<template >
<div class="sect__descriptionProjetP"  >
    <BoxTitleHome :title1="title1" :withText="true" :WithLink="false" :id-tag="'projets'"  />


    <BoxTitleHome :with-text="true" :-with-link="false" :title1="'+ projets'" :id-tag="'contact'" :colorBG="'sect__interTitreBox--posHaute'" />
</div>

</template>