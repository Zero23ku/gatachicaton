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
    import mockWednesday from '../assets/miercoles/mock.png'
    import mockThursday from '../assets/jueves/mock.png'
    import mockFriday from '../assets/viernes/mock.png'
    import mocchiS from '../assets/martes/mocchipinkusilueta.png'
    import mocchi from '../assets/martes/mocchipinku.png'
    import yun from '../assets/martes/YunCat.png'
    import yunS from '../assets/martes/YunCatsilueta.png'
    import moto from '../assets/martes/moto.png'
    import motoS from '../assets/martes/motosilueta.png'


    let froppyImg = ref(froppyS);
    let amakuImg = ref(amakuS);
    let meruImg = ref(meruS);
    let noxitoImg = ref(noxitoS);
    let z_klairImg = ref(z_klairS);
    let vremyaImg = ref(vremyaS);
    let mocchiImg = ref(mocchiS)
    let yunImg = ref(yunS)
    let motoImg = ref(motoS)
    let whosActive = ref(0)
    const props = defineProps(['day'])
    let socialNetworkMonday = ref("")
    let socialNetworkTuesday = ref("")
    const isMondayActive = true;
    const isTuesdayActive = false;

    function handleMouseOver(guest) {
        if(!isMondayActive){
            return
        }

        switch(guest) {
            case 1:
                froppyImg.value = froppy
                break;
            case 2:
                amakuImg.value = amaku
                break;
            case 3:
                meruImg.value = meru
                break;
            case 4:
                noxitoImg.value = noxito
                break;
            case 5:
                z_klairImg.value = z_klair
                break;
            case 6:
                vremyaImg.value = vremya
                break;
            case 7:
                if(isTuesdayActive) {
                    mocchiImg.value = mocchi
                }
                break;
            case 8:
                if(isTuesdayActive) {
                    yunImg.value = yun
                }
                break;
            case 9:
                if(isTuesdayActive) {
                    motoImg.value = moto
                }
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
            case 7:
                if(whosActive !== guest && isTuesdayActive){
                    mocchiImg.value = mocchiS
                }
                break;
            case 8:
                if(whosActive !== guest && isTuesdayActive){
                    yunImg.value = yunS
                }
                break;
            case 9:
                if(whosActive !== gues && isTuesdayActivet){
                    motoImg.value = motoS
                }
                break;
        }
    }

    function handleClick(guest) {
        hideEveryone()
        switch(guest) {
            case 1:
                froppyImg.value = froppy
                whosActive = 1
                socialNetworkMonday.value = 'https://x.com/iamfroppy'
                break;
            case 2:
                amakuImg.value = amaku
                whosActive = 2
                socialNetworkMonday.value = 'https://x.com/Amakuwu'
                break;
            case 3:
                meruImg.value = meru
                whosActive = 3
                socialNetworkMonday.value = 'https://x.com/Meruiwii'
                break;
            case 4:
                noxitoImg.value = noxito
                whosActive = 4
                socialNetworkMonday.value = 'https://x.com/N0cchi_'
                break;
            case 5:
                z_klairImg.value = z_klair
                whosActive = 5
                socialNetworkMonday.value = 'https://x.com/z_klair'
                break;
            case 6:
                vremyaImg.value = vremya
                whosActive = 6
                socialNetworkMonday.value = 'https://x.com/VremyasCourt'
                break;
            case 7:
                if(isTuesdayActive) {
                    mocchiImg.value = mocchi
                    whosActive = 7
                    socialNetworkTuesday.value = 'https://x.com/mocchipinku'
                }
                break;
            case 8:
                if(isTuesdayActive) {
                    yunImg.value = yun
                    whosActive = 8
                    socialNetworkTuesday.value = 'https://x.com/_YunCat'
                }
                break;
            case 9:
                if(isTuesdayActive) {
                    motoImg.value = moto
                    whosActive = 9
                    socialNetworkTuesday.value = 'https://x.com/Syko_Moto'
                }
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
        mocchiImg.value = mocchiS
        yunImg.value = yunS
        motoImg.value = motoS

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
            <a :href="socialNetworkMonday" target="_blank"> {{ socialNetworkMonday }} </a>
        </div>
        <div v-else class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 2" class="guest-details flex flex-col justify-center items-center">
        <div class="flex flex-col justify-center items-center">
            <img id="owowa" src="../assets/martes/owoa.png"/>
        </div>
        <div id="martes-container" class="bg-cover bg-center h-screen flex items-center justify-center">
            <div class="grid grid-row-1">
                <div id="guests-tuesday-first-row" class="flex flex-row items-center justify-center">
                    <img class="vtuber-tuesday-icon-first-row" :src="mocchiImg" @mouseover="handleMouseOver(7)" @mouseout='handleMouseOut(7)' @click='handleClick(7)'/>
                    <img class="vtuber-tuesday-icon-first-row" :src="yunImg" @mouseover='handleMouseOver(8)' @mouseout='handleMouseOut(8)' @click='handleClick(8)'/>
                    <img class="vtuber-tuesday-icon-second-row" :src="motoImg" @mouseover='handleMouseOver(9)' @mouseout='handleMouseOut(9)' @click='handleClick(9)'/>
                </div>
            </div>
        </div>
        <div v-if="isTuesdayActive" class="text-center">
            <a :href="socialNetworkTuesday" target="_blank"> {{ socialNetworkTuesday }} </a>
        </div>
        <div v-else class="coming-soon text-center">
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

    #owowa {
        position: relative; 
        top: 55%;
        left: -10%;
        width: 60%;
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

    #martes-container {
        background-image: url('../assets/martes/banner.png');
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

    .vtuber-tuesday-icon-first-row {
        max-width: 22%;
        height: auto;
        width: 100%;
        margin-right: 3%;
    }

    .vtuber-tuesday-icon-second-row {
        max-width: 22%;
        height: auto;
        width: 100%;
        margin-right: 4%;
    }

    #guests-first-row {
        padding-top: 3%;
        padding-left: 3%;
    }

    #guests-tuesday-first-row {
        padding-top: 3%;
        padding-left: 3%;
    }

    #guests-tuesday-second-row {

    }

    .coming-soon  {
        font-family: "Permanent Marker", cursive !important;
        font-size: 2.2vw !important;
    }

    .vtuber-icon-first-row, .vtuber-icon-second-row {
        cursor: pointer;
    }

    @media (max-width: 768px) {
        
        #guests h1, #helpus h1 {
            font-size: 10vw;
        }

        .coming-soon  {
            font-family: "Permanent Marker", cursive !important;
            font-size: 5vw !important;
        }

        a {
        font-size: 6.5vw;
        }
    }
</style>