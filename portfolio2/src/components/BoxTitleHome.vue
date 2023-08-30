<script setup>
import IconArrowMul1Vue from './icons/IconArrowMul1.vue';

const props = defineProps({
    title1 : String,
    title2 : String
})
</script>

<template>
    <div class="sect__titleBBox">
        <div class="titleBBox__decorBox">
            <svg xmlns="http://www.w3.org/2000/svg" width="52" height="52" viewBox="0 0 52 52" fill="none"
                class="titleBBox__svg1">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M51.2864 25.6459C51.2203 19.0298 48.5843 12.446 43.4171 7.51991C33.2676 -2.15607 17.1959 -1.7722 7.51991 8.37732C-2.15607 18.5268 -1.77219 34.5986 8.37732 44.2745C13.5445 49.2006 20.2467 51.5193 26.8584 51.2695C26.8624 51.3393 26.865 51.3757 26.865 51.3757C26.865 51.3757 26.8651 51.3392 26.8647 51.2692C33.2377 51.0268 39.5262 48.3978 44.2746 43.4171C49.0234 38.4359 51.3491 32.0281 51.2865 25.65C51.3564 25.6486 51.3928 25.6474 51.3928 25.6474C51.3928 25.6474 51.3564 25.6466 51.2864 25.6459ZM50.196 25.6536C50.7351 25.6591 51.1134 25.6536 51.2865 25.65C51.2864 25.6486 51.2864 25.6473 51.2864 25.6459C51.1132 25.6441 50.7348 25.6425 50.196 25.6536ZM50.196 25.6536C46.6354 25.6175 36.0578 25.1036 31.224 20.4164C26.5616 15.8954 25.5643 5.86399 25.3531 2.17C25.333 1.28857 25.297 0.76914 25.297 0.76914C25.297 0.76914 25.3027 1.28956 25.3531 2.17C25.4385 5.92472 25.235 16.2484 20.7314 20.9724C16.5523 25.356 7.38019 26.2713 3.08009 26.4555C1.65645 26.4461 0.769169 26.4974 0.769169 26.4974C0.769169 26.4974 1.65833 26.5164 3.08009 26.4555C7.35824 26.4837 16.48 27.0598 20.9223 31.2223C25.5324 35.5419 26.5666 45.0954 26.7983 49.3096C26.8079 50.314 26.8435 51.0146 26.8584 51.2695C26.8605 51.2694 26.8626 51.2693 26.8647 51.2692C26.8631 51.0141 26.8534 50.3133 26.7983 49.3096C26.7581 45.1194 27.1707 35.6409 31.4306 31.1724C36.019 26.3595 46.6265 25.7275 50.196 25.6536Z"
                    fill="#F7F1E8" />
            </svg>
        </div>
        <div class="titleBBox__titleB">
            <h2 class="sect__title sect__title--big sect__title--white">
                {{ title1 }}
            </h2>
            <svg xmlns="http://www.w3.org/2000/svg" width="82" height="85" viewBox="0 0 82 85" fill="none"
                class="titleBBox__svgD1">
                <path
                    d="M24.4797 32.9981C25.3488 32.3162 26.606 32.468 27.2878 33.337C27.9696 34.206 27.8179 35.4632 26.9489 36.145L24.4797 32.9981ZM4.32904 51.3508L3.32745 53.0819L0.769173 51.6017L3.09447 49.7773L4.32904 51.3508ZM52.322 77.4842C52.6069 78.5514 51.9727 79.6475 50.9055 79.9324L33.5146 84.5753C32.4474 84.8602 31.3513 84.226 31.0664 83.1588C30.7815 82.0916 31.4157 80.9955 32.4829 80.7106L47.9415 76.5836L43.8145 61.1251C43.5296 60.0579 44.1638 58.9618 45.231 58.6769C46.2981 58.3919 47.3942 59.0261 47.6791 60.0933L52.322 77.4842ZM26.9489 36.145L5.56361 52.9242L3.09447 49.7773L24.4797 32.9981L26.9489 36.145ZM5.33062 49.6196L51.3912 76.269L49.3881 79.7312L3.32745 53.0819L5.33062 49.6196Z"
                    fill="white" />
                <path d="M27.7891 2L64.5822 35.7152C70.6344 41.2611 66.7107 51.3507 58.5018 51.3507H4" stroke="white"
                    stroke-width="4" />
            </svg>
            <h3 class="sect__title sect__title--kuga sect__title--3 sect__title--white" style="opacity: 0.8;">
                {{ title2 }}
            </h3>
        </div>
        <IconArrowMul1Vue class="titleBBox__svgD2" />
    </div>
</template>

<style scoped lang="scss">
.sect {
    &__titleBBox {
        width: 100%;
        height: 80vh;
        border-radius: 50px 50px 0px 0px;
        background: #1D1D1D;
        padding: 3vh 5vw;
        background: url(../assets/images/texture1.jpg), lightgray 50% / cover no-repeat, url(../assets/images/texture2.jpg), lightgray 50% / cover no-repeat, #1D1D1D;
        position: relative;
    }


}

.titleBBox {

    &__decorBox {
        width: 90%;
        height: 20vh;
        display: flex;
        justify-content: flex-end;
        border-radius: 20px 20px 0px 0px;
        border-top: 2px solid #FDF8E9;
        border-left: 2px solid #FDF8E9;
    }

    &__svg1 {
        width: 50.781px;
        height: 50.781px;
        transform: translateX(7vw) translateY(-2vh);
    }

    &__svgD1 {
        position: absolute;
        right: 15px;
        top: 9vh;
    }

    &__svgD2 {
        position: absolute;
        left: 15px;
        top: 50vh;
        scale: 0.8;
        transform: rotateY(180deg);
    }

    &__titleB {

        transform: translateY(-7vh);
        margin: 0 0 0 8px;
        display: flex;
        flex-direction: column;
        row-gap: 8vh;
    }
}

@media(min-width: 900px) {

    .sect {
        &__titleBBox {
            width: 83%;
            height: 75vh;
            padding: 3vh 2vw;

            
        }
    }

    .titleBBox {
        &__decorBox {
            width: 98%;
            height: 40vh;
        }

        &__svg1 {
            transform: translateX(2vw) translateY(-1vh);
        }

        &__svgD1 {
            position: absolute;
            right: auto;
            left: 1vw;
            top: auto;
            bottom: 10%;
            transform: rotateY(180deg) scale(1.2);
        }

        &__svgD2 {
display: none;

        }

        &__titleB {

            transform: translateY(-22vh);
            row-gap: 3vh;
            &>h3{
                transform: translateX(10vw);
            }
        }
    }
}</style>
