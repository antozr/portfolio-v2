<script setup>
import SmallColInfoVue from '../components/SmallColInfo.vue';

</script>

<template>
    <div class="sect__project">

        <SmallColInfoVue :WithLink="false" :dataLink="'nameProject'" :WithBtn="true"/>
        <div class="sect__projetBoxImg">
            <div class="projetBI__containtImg">
                <div class="projetBI__imgBox">
                    <img src="https://images.unsplash.com/photo-1692936002249-2f0c5e2390c4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80"
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
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Magnam facilis dolores pariatur labore quia
                    numquam
                    ipsa. Ullam ab magni in?
                </p>
                <br />
                <p class="sect__txt">
                    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Amet quam numquam eum voluptatem explicabo?
                    Velit
                    reprehenderit perferendis iure ut blanditiis ullam, adipisci repellat! Magnam eos beatae tempore rerum
                    ipsa,
                    autem voluptate veniam, assumenda ut et totam, sapiente rem repellat possimus.
                </p>
            </div>
            <a href="#" class="projectDes__link">
                Voir le projet
            </a>
        </div>
    </div>
</template>