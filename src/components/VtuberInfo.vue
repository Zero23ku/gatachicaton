<script setup>
    import { ref } from 'vue';

    import amakuS from '../assets/lunes/amakusilueta.png'
    import froppyS from '../assets/lunes/froppysilueta.png'
    import meruS from '../assets/lunes/Merusilueta.png'
    import noxitoS from '../assets/lunes/noxitosilueta.png'
    import z_klairS from '../assets/lunes/z_klairsilueta.png'
    import vremyaS from '../assets/lunes/Vremyasilueta.png'
    import amaku from '../assets/lunes/amaku.png'
    import froppy from '../assets/lunes/froppy.png'
    import meru from '../assets/lunes/Meru.png'
    import noxito from '../assets/lunes/noxito.png'
    import z_klair from '../assets/lunes/Klair.png'
    import vremya from '../assets/lunes/Vremya.png'


    let froppyImg = ref(froppyS);
    let amakuImg = ref(amakuS);
    let meruImg = ref(meruS);
    let noxitoImg = ref(noxitoS);
    let z_klairImg = ref(z_klairS);
    let vremyaImg = ref(vremyaS);
    const props = defineProps(['imgSrc','link'])

  

</script>
<template>
    <!--<div class="guest-details flex flex-col justify-center items-center">
        <img style="width:400px" :src="imgSrc">
        <div class="-rotate-3">
        <a :href="link">{{ link }}</a>
        </div>
    </div>-->
    <div class="guest-details flex flex-col justify-center items-center">
        <div>
            <img src="../assets/lunes/titulo poke.png"/>
        </div>
        <div id="lunes-container" class="bg-cover bg-center">
            <div class="grid grid-row-2">
                <div id="guests-first-row" class="flex flex-row">
                    <img class="vtuber-icon-first-row" :src="froppyImg" @mouseover="froppyImg = froppy" @mouseout="froppyImg = froppyS"/>
                    <img class="vtuber-icon-first-row" :src="amakuImg" @mouseover="amakuImg = amaku" @mouseout="amakuImg = amakuS" />
                    <img class="vtuber-icon-first-row" :src="meruImg" @mouseover="meruImg=meru" @mouseout="meruImg=meruS"/>
                </div>
                <div id="guests-second-row" class="flex flex-row justify-end">
                    <img class="vtuber-icon-second-row" :src="noxitoImg" @mouseover="noxitoImg = noxito" @mouseout="noxitoImg = noxitoS"/>
                    <img class="vtuber-icon-second-row" :src="z_klairImg" @mouseover="z_klairImg = z_klair" @mouseout="z_klairImg = z_klairS"/>
                    <img class="vtuber-icon-second-row" :src="vremyaImg" @mouseover="vremyaImg = vremya" @mouseout="vremyaImg = vremyaS"/>
                </div>

            </div>
        </div>
    </div>
</template>
<style scoped>
    p {
        font-family: "Bebas Neue", sans-serif;
    }

    a {
        font-size: 35px
    }

    #lunes-container {
        background-image: url('../assets/lunes/fondo.png');
        max-width: 700px;
        max-height: 470px;
        width: 100%;
        height: auto;
        aspect-ratio: 500 / 270;
    }

    .vtuber-icon-first-row {
        max-width: 24%;
        height: auto;
        width: 100%;
        margin-right: 6%;
    }

    .vtuber-icon-second-row {
        max-width: 24%;
        height: auto;
        width: 100%;
        margin-right: 4%;
    }

    #guests-first-row {
        padding-top: 3%;
        padding-left: 3%;
    }
</style>