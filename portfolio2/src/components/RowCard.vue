<script setup>
import { ref } from 'vue';
import CardItem from './CardProjectSet.vue';
const props = defineProps({
    nbCard: Number,
    visible2: Boolean,
    visible3: Boolean
})

let datal = [{ name: 'lo' }, { name: 'la' }, { name: 'lu' }, { name: 'bite' }, { name: 'bite' }, { name: 'bite' }, { name: 'bite' }, { name: 'bite' }, { name: 'bite' }, { name: 'bite' }, { name: 'bite' }]
let dataRow = [];

</script>

<template>
    <div class="projetBox__rowListC" :v-show="visible2"
        :class="[visible2 ? 'projetBox__rowListC--start' : 'projetBox__rowListC--end']">

        <CardItem v-for="(data, index) in datal" :key="index + 1" :title-pr="data.name" :tagss="index"
            v-show="index <= 1" />
        <div class="projetBox__rowListC--reverse">
            <CardItem v-for="(data, index) in datal" :key="index" :title-pr="data.name" :tagss="index"
                v-show="index >= 2n && index <= 4n" small-card="cardProjet--small" />
        </div>
        <CardItem v-for="(data, index) in datal" :key="index" :title-pr="data.name" :tagss="index"
            v-show="index >= 5n && index <= 6" />
        <div class="projetBox__rowListC--reverse">
            <CardItem v-for="(data, index) in datal" :key="index" :title-pr="data.name" :tagss="index"
                v-show="index >= 7n && index <= 9n" small-card="cardProjet--small" />
        </div>

    </div>
</template>

