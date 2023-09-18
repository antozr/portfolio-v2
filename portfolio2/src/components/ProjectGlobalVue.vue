<script setup>
import { ref } from 'vue';
import IconLongBoxStar from './icons/IconLongBoxStar.vue';
import SmallColInfoVue from '../components/SmallColInfo.vue';

let allLinkAbout = [{ name: 'TFE', actif: true }, { name: 'Archeo', actif: false }, { name: 'CMG', actif: false }]
let allInfoProject = [
    {
        name: "TFE: TattooExplore",
        tag1: "Scolaire",
        tag2: "2023",
        des1: "lorem lorem",
        des2: "lorem",
        link: "https://tfe1-3.vercel.app/"
    }, {
        name: "Archeo : web-basement",
        tag1: "Event - 24h",
        tag2: "2023",
        des1: "lorem lorem",
        des2: "lorem",
        subLink : [1,2,3],
        link: "http://antoni-dumont.be/projets/wb/"
    }, {
        name: "Chatterie du Monde de Gioia",
        tag1: "Client",
        tag2: "2023",
        des1: "lorem lorem",
        des2: "lorem",
        link: "https://cmg-inky.vercel.app/"
    },
];

const itemData = ref(0);
function updateItemList(e) {
    if (e.target.innerText === allLinkAbout[0].name) {
        itemData.value = 0
    } else if (e.target.innerText === allLinkAbout[1].name) {
        itemData.value = 1
    } else if (e.target.innerText === allLinkAbout[2].name) {
        itemData.value = 2
    } else if (e.target.innerText === allLinkAbout[3].name) {
        itemData.value = 3
    }
    else {
        itemData.value = 0
    }
};
function changeStateElNav(e) {
    let allLinkek = document.querySelectorAll('.boxSLLink--allEL')
    allLinkek.forEach((el) => {
        el.classList.remove('boxSLLink__el--actif');

    });
    console.log(e);
    if (e.target.classList == 'boxSLLink--allEL') {

        e.target.classList.add('boxSLLink__el--actif');

    }
}
</script>

<template>
    <div class="sect__project">
        <div class="sect__boxSmallLLink" >
            <IconLongBoxStar />
            <div class="boxSLLink__boxNav">
                <ul class="boxSLLink__list">
                    <li class="boxSLLink__el" v-for="(item, index) in allLinkAbout" :key="index"
                        v-on:click="updateItemList">

                        <p :class="[item.actif ? ' boxSLLink__el--actif boxSLLink--allEL ' : 'boxSLLink--allEL']"
                            v-on:click="changeStateElNav">
                            {{ item.name }}
                        </p>
                    </li>
                </ul>

                <RouterLink to="/projets" class="boxSLLink__linkBtn" v-show="WithBtn">

                    Tous voir
                </RouterLink>

            </div>
            <div class="boxSLLink__boxDec1">
                <IconRoundStar />
            </div>
        </div>
        <!--<SmallColInfoVue :WithLink="false" :dataLink="'nameProject'" :WithBtn="true"/>-->
        <div class="sect__projetBoxImg">
            <div class="projetBI__containtImg">
                <div class="projetBI__imgBox">
                    <img src="../assets/images/archeo1.jpg"
                        alt="This is in screenshot of my project." class="projetBI__img" loading="lazy">
                </div>
            </div>

            <div class="projetBI__boxTitleI">
                <h2 class="sect__title--kuga sect__title sect__title--2">
                    {{ allInfoProject[itemData].name }}
                </h2>
                <ul class="projetBI__listTagT">
                    <li class="projetBI__elTag sect__txt">
                        {{ allInfoProject[itemData].tag1 }}
                    </li>
                    <li class="projetBI__elTag sect__txt">
                        {{ allInfoProject[itemData].tag2 }}
                    </li>
                </ul>
            </div>

        </div>
        <div class="sect__projectDes">
            <div class="projectDes__boxT">
                <p class="sect__txt sect__txt--bigW">
                    {{ allInfoProject[itemData].des1 }}
                </p>
                <br />
                <p class="sect__txt">
                    {{ allInfoProject[itemData].des2}}
                <a :href="item" v-show="allInfoProject[itemData].subLink" v-for="(item, index) in allInfoProject[itemData].subLink" :key="index">{{item}} </a>
                </p>
            </div>
            <a :href=" allInfoProject[itemData].link" target="_blank" class="projectDes__link">
                Voir le projet
            </a>
        </div>
    </div>
</template>