<script setup>
import { ref } from 'vue';
import CardItem from './CardProjectSet.vue';
import dataPortfolio from '../assets/data/donnee_portfolio.json';
import dataProjets from '../assets/data/data-Projets.json';
const props = defineProps({
    nbCard: Number,
    visible2: Boolean,
    visible3: Boolean
})


console.table(dataProjets)
</script>

<template>
    <div class="projetBox__rowListC" :v-show="visible2"
        :class="[visible2 ? 'projetBox__rowListC--start' : 'projetBox__rowListC--end']">

        <CardItem v-for="(data, index) in dataProjets" :key="index + 1" :title-pr="data.titleShort" :tagss="data.tag1" :title-sd="data.titleShort"
            :tags2="data.tag2" :description="data.txt1[0]" v-show="index <= 1" :linkPr="data.urlSite" />
        <div class="projetBox__rowListC--reverse">
            <CardItem v-for="(data, index) in dataProjets" :key="index" :title-pr="data.titleShort" :tagss="data.tag1" :title-sd="data.titleShort"
                :tags2="data.tag2" :description="data.txt1[0]" :linkPr="data.urlSite" v-show="index >= 2n && index <= 4n"
                small-card="cardProjet--small" />
        </div>
        <CardItem v-for="(data, index) in dataProjets" :key="index" :title-pr="data.titleShort" :tagss="data.tag1" :title-sd="data.titleShort"
            :tags2="data.tag2" :description="data.txt1[0]" :linkPr="data.urlSite" v-show="index >= 5n && index <= 6" />
        <div class="projetBox__rowListC--reverse">
            <CardItem v-for="(data, index) in dataProjets" :key="index" :title-pr="data.titleShort" :tagss="data.tag1" :title-sd="data.titleShort"
                :tags2="data.tag2" :description="data.txt1[0]" :linkPr="data.urlSite" v-show="index >= 7n && index <= 9n"
                small-card="cardProjet--small" />
        </div>

    </div>
</template>

