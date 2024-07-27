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
    import mockTuesday from '../assets/martes/mock.png'
    import mockWednesday from '../assets/miercoles/mock.png'
    import mockThursday from '../assets/jueves/mock.png'
    import mockFriday from '../assets/viernes/mock.png'


    let froppyImg = ref(froppyS);
    let amakuImg = ref(amakuS);
    let meruImg = ref(meruS);
    let noxitoImg = ref(noxitoS);
    let z_klairImg = ref(z_klairS);
    let vremyaImg = ref(vremyaS);
    let whosActive = ref(0)
    const props = defineProps(['day'])
    let socialNetwork = ref("")
    const isMondayActive = false;

    function handleMouseOver(guest) {
        if(!isMondayActive){
            return
        }

        switch(guest) {
            case 1:
                froppyImg.value = froppy
                //socialNetwork = 'Tuiter de Froppy'
                break;
            case 2:
                amakuImg.value = amaku
                //socialNetwork = 'Tuiter de Amaku'
                break;
            case 3:
                meruImg.value = meru
                //socialNetwork = 'Tuiter de Froppy'
                break;
            case 4:
                noxitoImg.value = noxito
                //socialNetwork = 'Tuiter de Noxito'
                break;
            case 5:
                z_klairImg.value = z_klair
                //socialNetwork = 'Tuiter de z_klair'
                break;
            case 6:
                vremyaImg.value = vremya
                //socialNetwork = 'Tuiter de Vremya'
                break;
        }
    }

    function handleMouseOut(guest) {
        if(!isMondayActive){
            return
        }

        switch(guest) {
            case 1:
                if(whosActive !== guest) {
                    froppyImg.value = froppyS
                }
                
                break;
            case 2:
                if(whosActive !== guest) {
                    amakuImg.value = amakuS
                }
                break;
            case 3:
                if(whosActive !== guest) {
                    meruImg.value = meruS
                }
                break;
            case 4:
                if(whosActive !== guest) {
                    noxitoImg.value = noxitoS
                }
                break;
            case 5:
                if(whosActive !== guest) {
                    z_klairImg.value = z_klairS
                }
                break;
            case 6:
                if(whosActive !== guest) {
                    vremyaImg.value = vremyaS
                }
                break;
        }
    }

    function handleClick(guest) {
        if(!isMondayActive){
            return
        }
        hideEveryone()
        switch(guest) {
            case 1:
                froppyImg.value = froppy
                whosActive = 1
                socialNetwork.value = 'Tuiter de Froppy'
                break;
            case 2:
                amakuImg.value = amaku
                whosActive = 2
                socialNetwork.value = 'Tuiter de Amaku'
                break;
            case 3:
                meruImg.value = meru
                whosActive = 3
                socialNetwork.value = 'Tuiter de Meru'
                break;
            case 4:
                noxitoImg.value = noxito
                whosActive = 4
                socialNetwork.value = 'Tuiter de Noxito'
                break;
            case 5:
                z_klairImg.value = z_klair
                whosActive = 5
                socialNetwork.value = 'Tuiter de z_klair'
                break;
            case 6:
                vremyaImg.value = vremya
                whosActive = 6
                socialNetwork.value = 'Tuiter de Vremya'
                break;
        }
    }

    function hideEveryone() {
        froppyImg.value = froppyS
        amakuImg.value = amakuS
        meruImg.value = meruS
        noxitoImg.value = noxitoS
        z_klairImg.value = z_klairS
        vremyaImg.value = vremyaS
    }


</script>
<template>

    <div v-if="props.day == 1" class="guest-details flex flex-col justify-center items-center">
        <div class="flex flex-col justify-center items-center">
            <img id="pokedibujo" src="../assets/lunes/titulo poke.png"/>
        </div>
        <div id="lunes-container" class="bg-cover bg-center">
            <div class="grid grid-row-2">
                <div id="guests-first-row" class="flex flex-row">
                    <img class="vtuber-icon-first-row" :src="froppyImg" @mouseover="handleMouseOver(1)" @mouseout='handleMouseOut(1)' @click='handleClick(1)'/>
                    <img class="vtuber-icon-first-row" :src="amakuImg" @mouseover='handleMouseOver(2)' @mouseout='handleMouseOut(2)' @click='handleClick(2)'/>
                    <img class="vtuber-icon-first-row" :src="meruImg" @mouseover='handleMouseOver(3)' @mouseout='handleMouseOut(3)' @click='handleClick(3)'/>
                </div>
                <div id="guests-second-row" class="flex flex-row justify-end">
                    <img class="vtuber-icon-second-row" :src="noxitoImg" @mouseover='handleMouseOver(4)' @mouseout='handleMouseOut(4)' @click='handleClick(4)'/>
                    <img class="vtuber-icon-second-row" :src="z_klairImg" @mouseover='handleMouseOver(5)' @mouseout='handleMouseOut(5)' @click='handleClick(5)'/>
                    <img class="vtuber-icon-second-row" :src="vremyaImg" @mouseover='handleMouseOver(6)' @mouseout='handleMouseOut(6)' @click='handleClick(6)'/>
                </div>

            </div>
        </div>
        <div v-if="isMondayActive" class="text-center">
            <a href="#"> {{ socialNetwork }} </a>
        </div>
        <div v-else class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 2">
        <div class="flex flex-col justify-center items-center">
            <img id="martesS" :src="mockTuesday"/>
        </div>
        <div class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 3">
        <div class="flex flex-col justify-center items-center">
            <img id="miercolesS" :src="mockWednesday"/>
        </div>
        <div class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 4">
        <div class="flex flex-col justify-center items-center">
            <img id="juevesS" :src="mockThursday"/>
        </div>
        <div class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 5">
        <div class="flex flex-col justify-center items-center">
            <img id="viernesS" :src="mockFriday"/>
        </div>
        <div class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
</template>
<style scoped>
    p{
        font-family: "Bebas Neue", sans-serif;
    }

    h1 {
        font-family: "Permanent Marker", cursive;;
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
        margin-bottom: 10px;
        aspect-ratio: 500 / 270;
    }

    #pokedibujo {
        max-width: 50%;
        margin-bottom: 10px;
    }

    #martesS, #miercolesS, #juevesS, #viernesS {
        max-width: 50%;
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

    .coming-soon  {
        font-family: "Permanent Marker", cursive !important;
        font-size: 2.2vw !important;
    }

    @media (max-width: 768px) {
        
        #guests h1, #helpus h1 {
            font-size: 10vw;
        }

        .coming-soon  {
            font-family: "Permanent Marker", cursive !important;
            font-size: 5vw !important;
        }
    }
</style>