<script setup>
import IconEmail from './icons/IconMail1.vue';
import IconIN from './icons/IconLinkdin.vue';
import IconGithub from './icons/IconGithub.vue';
import IconBoxStar from './icons/IconRoundStar1.vue';



let allLink = [
    {
        link: "mailto:antonidwm@gmail.com",
        name: "antonidwm@gmail.com",
        icon: 0
    }, {
        link: "https://github.com/antozr",
        name: "antozr",
        icon: 1
    }, {
        link: "https://www.linkedin.com/in/antoni-dumont-2724ba251/",
        name: "Antoni Dumont",
        icon: 2
    }
]
</script>


<template>
    <section class="sect__contactBox">
        <div class="contactBox__left">
            <div class="contactBox__decorB">
                <IconBoxStar></IconBoxStar>
            </div>
            <ul class="contactBox__linkList">
                <li class="contactBox__elLink" v-for="(item, index) in allLink" :key="index">

                    <a :href="item.link" class="contactBox__link">
                        <IconEmail v-show="item.icon == 0" class="contactBox__elSvg" />
                        <IconIN v-show="item.icon == 2" class="contactBox__elSvg" />
                        <IconGithub v-show="item.icon == 1" class="contactBox__elSvg" /> {{ item.name }}
                    </a>
                </li>
            </ul>
        </div>
        <div class="contactBox__rightBox">
            <p class="sect__title sect__title--kuga sect__title--2">
                A la prochaine
            </p>
        </div>
    </section>
</template>