<script setup>
import { ref } from 'vue';
import IconLongBoxStar from './icons/IconLongBoxStar.vue';
import SmallColInfoVue from '../components/SmallColInfo.vue';
import archeo1 from '../assets/images/archeo1.jpg';
import tfe1 from '../assets/images/tfe1.jpg';
import cmg1 from '../assets/images/cmg1.jpg';

let allLinkAbout = [{ name: 'TFE', actif: true }, { name: 'Archeo', actif: false }, { name: 'CMG', actif: false }]
let allInfoProject = [
    {
        name: "TFE: TattooExplore",
        tag1: "Scolaire",
        tag2: "2023",
        des1: "Une exploration dans l’histoire des différents styles de tatouage dans le monde .",
        des2: "Voici mon projet de fin d’étude, un site multi-pages, où l’objectif était de créer des pages modulables et facile à rajouter ou changer les informations. Pour ce faire, j’ai travaillé avec React.js ainsi que certaines bibliothèques (Framer.motion, React router v6…). Mon objectif a été de créer diverse composants modulables par les « options » qu’on lui rentre. Comme cela, on part d’un même bloque pour avoir diverse options.",
        link: "https://tfe1-3.vercel.app/",
        subLink:[{
            name: 'Le github du projet',
            link:"https://github.com/antozr/tfe1.3"
        }],
        imgTag:0
    }, {
        name: "Archeo : web-basement",
        tag1: "Event - 24h",
        tag2: "2023",
        des2: 'Le but ? Ce fut de répondre à un postulat un peu perché, mais qui peut se résumer à « qu’avons-nous fait dans le présent qui à impacter le passé et qu’on a vus dans le futur ? ». Sur la base de ce postulat, avec le groupe et la bonne ambiance de la fête, nous sommes partis à la création de ce projet, simple mais avec ces subtilités graphiques à mettre en place. J’ai alors pris le rôle d’intégrer le projet, avec un test sur react.js, pour une faciliter de faire les articles, du changement des pages mais aussi pour essayer de nouvelles méthodes pour la gestion de pages similaires mais au contenu différent. ',
        des1: "Une aventure de 24h, avec des potes pour un projet déjanté.",
        // subLink : [{
        //     name:'Jean de Roy',
        //     link: "https://caeiinos.be/"
        // },{
        //     name: 'Thunus Bastien',
        // }],
        link: "http://antoni-dumont.be/projets/wb/",
        imgTag:1
    }, {
        name: "Chatterie du Monde de Gioia",
        tag1: "Client",
        tag2: "2023",
        des1: "Un premier projet pour un client, pour une chatterie remplie de boules de poils. ",
        des2: "Pour cette demande, ce fut assez simple, mettre en place un site pour présenter la chatterie, les chats, les chatons mais aussi donner des infos pratiques & importantes sur les conditions d’adoptions et les réglementations à accepter. Pour ce faire, j’ai analysé les différents sites de chatterie, pour en retirer le meilleur mais aussi pour faire quelque chose en accord avec les règles UI /UX. Une simplicité graphique pour mettre en valeur les chats, les photos mais aussi pour adoucir visuellement les différentes informations qu’on y retrouve. ",
        link: "https://cmg-inky.vercel.app/",
        imgTag:2
    },
];

let allImg= ["https://antoni-dumont.be/projets/portfolio/img/tfe1-33b6b41b.jpg","https://antoni-dumont.be/projets/portfolio/img/archeo1-09d7be02.jpg","https://antoni-dumont.be/projets/portfolio/img/cmg1-3e8c3327.jpg"];

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

                <RouterLink to="/projets" class="boxSLLink__linkBtn" v-show="true">

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
                    <img :src="allImg[allInfoProject[itemData].imgTag]"
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
                    {{ allInfoProject[itemData].des2}} <br/>
                <a :href="item.link" v-show="allInfoProject[itemData].subLink" v-for="(item, index) in allInfoProject[itemData].subLink" :key="index">{{item.name}} </a>
                </p>
            </div>
            <a :href=" allInfoProject[itemData].link" target="_blank" class="projectDes__link">
                Voir le projet
            </a>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.projectDes{

    &__boxT{
        margin: 28px 0 18px;
    }
}



@media(min-width:900px){
    .projectDes{

&__boxT{
    margin:  0;
}
}
}
</style>

