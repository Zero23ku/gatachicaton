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
    import mocchiS from '../assets/martes/mocchipinkusilueta.png'
    import mocchi from '../assets/martes/mocchipinku.png'
    import yun from '../assets/martes/YunCat.png'
    import yunS from '../assets/martes/YunCatsilueta.png'
    import moto from '../assets/martes/moto.png'
    import motoS from '../assets/martes/motosilueta.png'
    import gishi from '../assets/miercoles/gishi.png'
    import gishiS from '../assets/miercoles/gishi_silueta.png'
    import retniw from '../assets/miercoles/retniw_.png'
    import retniwS from '../assets/miercoles/retniw_silueta.png'
    import retniwsThursdayS from '../assets/jueves/retniwsilueta.png'
    import retniwsThursday from '../assets/jueves/Resniu.png'
    import pupaS from '../assets/jueves/pupasilueta.png'
    import pupa from '../assets/jueves/Pupa.png'
    import ptext from '../assets/jueves/ptext.png'
    import rtext from '../assets/jueves/rtext.png'
    import retniwFridayS from '../assets/viernes/resniusilueta.png'
    import retniwFriday from '../assets/viernes/resniu.png'
    import nanaS from '../assets/viernes/nanasilueta.png'
    import nana from '../assets/viernes/nana.png'
    import rtextf from '../assets/viernes/retniwtext.png'
    import ntext from '../assets/viernes/nanatext.png'
    import harpuia from '../assets/sabado/hardpollas.png'
    import harpuiaS from '../assets/sabado/harpuiasilueta.png'
    import mercury from '../assets/sabado/mercury.png'
    import mercuryS from '../assets/sabado/mercurysilueta.png'
    import remmus from '../assets/sabado/remmus.png'
    import remmusS from '../assets/sabado/remmussilueta.png'



    let froppyImg = ref(froppyS);
    let amakuImg = ref(amakuS);
    let meruImg = ref(meruS);
    let noxitoImg = ref(noxitoS);
    let z_klairImg = ref(z_klairS);
    let vremyaImg = ref(vremyaS);
    let mocchiImg = ref(mocchiS)
    let yunImg = ref(yunS)
    let motoImg = ref(motoS)
    let gishiImg = ref(gishiS)
    let retniwImg = ref(retniwS)
    let retniwThursdayImg = ref(retniwsThursdayS)
    let pupaImg = ref(pupaS)
    let retniwFridayImg = ref(retniwFridayS)
    let nanaImg = ref(nanaS)
    let harpuiaImg = ref(harpuiaS)
    let remmusImg = ref(remmusS)
    let mercuryImg = ref(mercuryS)
    let whosActive = ref(0)
    let hiderText = false
    let hidepText = false
    let hidenText = false
    let hiderTextF = false
    const props = defineProps(['day'])
    let socialNetworkMonday = ref("")
    let socialNetworkTuesday = ref("")
    let socialNetworkWednesday = ref("")
    let socialNetworkThursday = ref("")
    let socialNetworkFriday = ref("")
    let socialNetworkSaturday = ref("")
    const isMondayActive = true;
    const isTuesdayActive = true
    const isWednesdayActive = true
    const isThursdayActive = true
    const isFridayActive = true
    const isSaturdayActive = true
    
    const isSundayActive = false

    function handleMouseOver(guest) {
        switch(guest) {
            case 1:
                froppyImg.value = froppy
                break
            case 2:
                amakuImg.value = amaku
                break
            case 3:
                meruImg.value = meru
                break
            case 4:
                noxitoImg.value = noxito
                break
            case 5:
                z_klairImg.value = z_klair
                break
            case 6:
                vremyaImg.value = vremya
                break
            case 7:
                if(isTuesdayActive) {
                    mocchiImg.value = mocchi
                }
                break
            case 8:
                if(isTuesdayActive) {
                    yunImg.value = yun
                }
                break
            case 9:
                if(isTuesdayActive) {
                    motoImg.value = moto
                }
                break
            case 10:
                if(isWednesdayActive) {
                    gishiImg.value = gishi
                }
                break
            case 11:
                if(isWednesdayActive) {
                    retniwImg.value = retniw
                }
                break
            case 12:
                if(isThursdayActive) {
                    retniwThursdayImg.value = retniwsThursday
                    hiderText = true
                }
                break
            case 13:
                if(isThursdayActive) {
                    pupaImg.value = pupa
                    hidepText = true
                }
                break
            case 14:
                if(isFridayActive) {
                    nanaImg.value = nana
                    hidenText = true
                }
                break
            case 15:
                if(isFridayActive) {
                    retniwFridayImg.value = retniwFriday
                    hiderTextF = true
                }
                break
            case 16:
                if(isSaturdayActive) {
                    harpuiaImg.value = harpuia
                }
                break
            case 17:
                if(isSaturdayActive) {
                    mercuryImg.value = mercury
                }
                break
            case 18:
                if(isSaturdayActive) {
                    remmusImg.value = remmus
                }
                break
        }
    }

    function handleMouseOut(guest) {

        switch(guest) {
            case 1:
                if(whosActive !== guest) {
                    froppyImg.value = froppyS
                }
                break
            case 2:
                if(whosActive !== guest) {
                    amakuImg.value = amakuS
                }
                break
            case 3:
                if(whosActive !== guest) {
                    meruImg.value = meruS
                }
                break
            case 4:
                if(whosActive !== guest) {
                    noxitoImg.value = noxitoS
                }
                break
            case 5:
                if(whosActive !== guest) {
                    z_klairImg.value = z_klairS
                }
                break
            case 6:
                if(whosActive !== guest) {
                    vremyaImg.value = vremyaS
                }
                break
            case 7:
                if(whosActive !== guest && isTuesdayActive){
                    mocchiImg.value = mocchiS
                }
                break
            case 8:
                if(whosActive !== guest && isTuesdayActive){
                    yunImg.value = yunS
                }
                break
            case 9:
                if(whosActive !== guest && isTuesdayActive){
                    motoImg.value = motoS
                }
                break
            case 10:
                if(whosActive !== guest && isWednesdayActive) {
                    gishiImg.value = gishiS
                }
                break
            case 11:
                if(whosActive !== guest && isWednesdayActive) {
                    retniwImg.value = retniwS
                }
                break
            case 12:
                if(whosActive !== guest && isThursdayActive) {
                    retniwThursdayImg.value = retniwsThursdayS
                    hiderText = false
                }
                break
            case 13:
                if(whosActive !== guest && isThursdayActive) {
                    pupaImg.value = pupaS
                    hidepText = false
                }
                break
            case 14:
                if(whosActive !== guest && isFridayActive) {
                    nanaImg.value = nanaS
                    hidenText = false
                }
                break
            case 15:
                if(whosActive !== guest && isFridayActive) {
                    retniwFridayImg.value = retniwFridayS
                    hiderTextF = false
                }
                break
            case 16:
                if(whosActive !== guest && isSaturdayActive) {
                    harpuiaImg.value = harpuiaS
                }
                break
            case 17:
                if(whosActive !== guest && isSaturdayActive) {
                    mercuryImg.value = mercuryS
                }
                break
            case 18:
                if(whosActive !== guest && isSaturdayActive) {
                    remmusImg.value = remmusS
                }
                break
        }
    }

    function handleClick(guest) {
        hideEveryone(guest)
        switch(guest) {
            case 1:
                froppyImg.value = froppy
                whosActive = 1
                socialNetworkMonday.value = 'https://x.com/iamfroppy'
                break
            case 2:
                amakuImg.value = amaku
                whosActive = 2
                socialNetworkMonday.value = 'https://x.com/Amakuwu'
                break
            case 3:
                meruImg.value = meru
                whosActive = 3
                socialNetworkMonday.value = 'https://x.com/Meruiwii'
                break
            case 4:
                noxitoImg.value = noxito
                whosActive = 4
                socialNetworkMonday.value = 'https://x.com/N0cchi_'
                break
            case 5:
                z_klairImg.value = z_klair
                whosActive = 5
                socialNetworkMonday.value = 'https://x.com/z_klair'
                break
            case 6:
                vremyaImg.value = vremya
                whosActive = 6
                socialNetworkMonday.value = 'https://x.com/VremyasCourt'
                break
            case 7:
                if(isTuesdayActive) {
                    mocchiImg.value = mocchi
                    whosActive = 7
                    socialNetworkTuesday.value = 'https://x.com/mocchipinku'
                }
                break
            case 8:
                if(isTuesdayActive) {
                    yunImg.value = yun
                    whosActive = 8
                    socialNetworkTuesday.value = 'https://x.com/_YunCat'
                }
                break
            case 9:
                if(isTuesdayActive) {
                    motoImg.value = moto
                    whosActive = 9
                    socialNetworkTuesday.value = 'https://x.com/Syko_Moto'
                }
                break
            case 10:
                if(isWednesdayActive) {
                    gishiImg.value = gishi
                    whosActive = 10
                    socialNetworkWednesday.value = 'https://x.com/Gishimonn'
                }
                break
            case 11:
                if(isWednesdayActive) {
                    retniwImg.value = retniw
                    whosActive = 11
                    socialNetworkWednesday.value = 'https://x.com/RetniwVT'
                }
                break
            case 12:
                if(isThursdayActive) {
                    retniwThursdayImg.value = retniwsThursday
                    whosActive = 12
                    socialNetworkThursday.value = 'https://x.com/RetniwVT'
                    hiderText = true
                }
                break
            case 13:
                if(isThursdayActive) {
                    pupaImg.value = pupa
                    whosActive = 13
                    socialNetworkThursday.value = 'https://x.com/puparoid'
                    hidepText = true
                }
                break
            case 14:
                if(isFridayActive) {
                    nanaImg.value = nana
                    whosActive = 14
                    socialNetworkFriday.value = 'https://x.com/Nana_Hare0'
                    hidenText = true
                }
                break
            case 15:
                if(isFridayActive) {
                    retniwFridayImg.value = retniwFriday
                    whosActive = 15
                    socialNetworkFriday.value = 'https://x.com/RetniwVT'
                    hiderTextF = true
                }
                break
            case 16:
                if(isSaturdayActive) {
                    harpuiaImg.value = harpuia
                    whosActive = 16
                    socialNetworkSaturday.value = 'https://x.com/HarpuiaVT'
                }
                break
            case 17:
                if(isSaturdayActive) {
                    meruImg.value = mercury
                    whosActive = 17
                    socialNetworkSaturday.value = 'https://x.com/ItsMercuryVT'
                }
                break
            case 18:
                if(isSaturdayActive) {
                    remmusImg.value = remmus
                    whosActive = 18
                    socialNetworkSaturday.value = 'https://x.com/RemmusCobalt'
                }
                break
        }
    }

    function hideEveryone(guest) {
        if(guest !== 1) {
            froppyImg.value = froppyS
        }
        if(guest !== 2) {
            amakuImg.value = amakuS
        }
        if(guest !== 3) {
            meruImg.value = meruS
        }
        if(guest !== 4) {
            noxitoImg.value = noxitoS
        }
        if(guest !== 5) {
            z_klairImg.value = z_klairS
        }
        if(guest !== 6) {
            vremyaImg.value = vremyaS
        }
        if(guest !== 7) {
            mocchiImg.value = mocchiS
        }
        if(guest !== 8) {
            yunImg.value = yunS
        }
        if(guest !== 9) {
            motoImg.value = motoS
        }
        if(guest !== 10) {
            gishiImg.value = gishiS
        }
        if(guest !== 11) {
            retniwImg.value = retniwS
        }
        if(guest !== 12) {
            retniwThursdayImg.value = retniwsThursdayS
            hiderText = false
        }
        if(guest !== 13) {
            pupaImg.value = pupaS
            hidepText = false
        }
        if(guest !== 14) {
            nanaImg.value = nanaS
            hidenText = false
        }
        if(guest !== 15) {
            retniwFridayImg.value = retniwFridayS
            hiderTextF = false
        }
        if(guest !== 16) {
            harpuiaImg.value = harpuiaS
        }
        if(guest !== 17) {
            mercuryImg.value = mercuryS
        }
        if(guest !== 18) {
            remmusImg.value = remmusS
        }
     
        socialNetworkMonday.value = ""
        socialNetworkTuesday.value = ""
        socialNetworkTuesday.value = ""
        socialNetworkThursday.value = ""
        socialNetworkFriday.value = ""
        socialNetworkSaturday.value = ""
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
    <div v-if="props.day == 3" class="guest-details flex flex-col justify-center items-center">
        <div class="flex flex-col justify-center items-center">
            <img id="dibujos_2x1" src="../assets/miercoles/DIBUJOS_x_SUB.png"/>
        </div>
        <div id="miercoles-container" class="bg-cover bg-center h-screen flex items-center justify-center">
            <div class="grid grid-row-1">
                <div id="guests-wednesday-first-row" class="flex flex-row items-center justify-center">
                    <img class="vtuber-wednesday-icon-first-row" :src="gishiImg" @mouseover="handleMouseOver(10)" @mouseout='handleMouseOut(10)' @click='handleClick(10)'/>
                    <img class="vtuber-wednesday-icon-first-row" :src="retniwImg" @mouseover='handleMouseOver(11)' @mouseout='handleMouseOut(11)' @click='handleClick(11)'/>
                </div>
            </div>
        </div>
        <div v-if="isWednesdayActive" class="text-center">
            <a :href="socialNetworkWednesday" target="_blank"> {{ socialNetworkWednesday }} </a>
        </div>
        <div v-else class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 4" class="guest-details flex flex-col justify-center items-center">
        <div class="flex flex-col justify-center items-center">
            <img id="dibujos_2x1" src="../assets/jueves/testoxs.png"/>
        </div>
        <div id="jueves-container" class="bg-cover bg-center h-screen flex items-center justify-center">
            <div class="grid grid-row-1">
                <div id="guests-thursday-first-row" class="flex flex-row items-center justify-center">
                    <img class="vtuber-thursday-icon-first-row" :src="retniwThursdayImg" @mouseover="handleMouseOver(12)" @mouseout='handleMouseOut(12)' @click='handleClick(12)'/>
                    <img class="vtuber-thursday-pupa-icon-first-row" :src="pupaImg" @mouseover='handleMouseOver(13)' @mouseout='handleMouseOut(13)' @click='handleClick(13)'/>
                </div>
                <div id="guests-thursday-second-row" class="flex flex-row items-center justify-center">
                    <img class="vtuber-thursday-rtext-second-row" :class="{'invisible' : !hiderText}" :src="rtext"/>
                    <img class="vtuber-thursday-ptext-second-row" :class="{'invisible' : !hidepText}" :src="ptext"/>
                </div>
            </div>
        </div>
        <div v-if="isThursdayActive" class="text-center">
            <a :href="socialNetworkThursday" target="_blank"> {{ socialNetworkThursday }} </a>
        </div>
        <div v-else class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 5" class="guest-details flex flex-col justify-center items-center">
        <div class="flex flex-col justify-center items-center">
            <img id="watchparty-titulo" src="../assets/viernes/testo_viernes.png"/>
        </div>
        <div id="viernes-container" class="bg-cover bg-center h-screen flex items-center justify-center">
            <div class="grid grid-row-1">
                <div id="guests-friday-first-row" class="flex flex-row items-center justify-center">
                    <img class="vtuber-friday-icon-first-row" :src="nanaImg" @mouseover='handleMouseOver(14)' @mouseout='handleMouseOut(14)' @click='handleClick(14)'/>
                    <img class="vtuber-friday-icon-first-row" :src="retniwFridayImg" @mouseover='handleMouseOver(15)' @mouseout='handleMouseOut(15)' @click='handleClick(15)'/>
                </div>
                <div id="guests-friday-second-row" class="flex flex-row items-center justify-center">
                    <img class="vtuber-friday-ntext-second-row" :class="{'invisible' : !hidenText}" :src="ntext"/>
                    <img class="vtuber-friday-rtext-second-row" :class="{'invisible' : !hiderTextF}" :src="rtextf"/>
                </div>
            </div>
        </div>
        <div v-if="isFridayActive" class="text-center">
            <a :href="socialNetworkFriday" target="_blank"> {{ socialNetworkFriday }} </a>
        </div>
        <div v-else class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 6" class="guest-details flex flex-col justify-center items-center">
        <div class="flex flex-col justify-center items-center">
            <img id="contentw-titulo" src="../assets/sabado/texts.png"/>
        </div>
        <div id="sabado-container" class="bg-cover bg-center h-screen flex items-center justify-center">
            <div class="grid grid-row-1">
                <div id="guests-saturday-first-row" class="flex flex-row items-center justify-center">
                    <img class="vtuber-saturday-icon-first-row" :src="harpuiaImg" @mouseover='handleMouseOver(16)' @mouseout='handleMouseOut(16)' @click='handleClick(16)'/>
                    <img class="vtuber-saturday-icon-first-row" :src="mercuryImg" @mouseover='handleMouseOver(17)' @mouseout='handleMouseOut(17)' @click='handleClick(17)'/>
                    <img class="vtuber-saturday-icon-first-row vtuber-saturday-icon-first-row-last" :src="remmusImg" @mouseover='handleMouseOver(18)' @mouseout='handleMouseOut(18)' @click='handleClick(18)'/>
                </div>
            </div>
        </div>
        <div v-if="isSaturdayActive" class="text-center">
            <a :href="socialNetworkSaturday" target="_blank"> {{ socialNetworkSaturday }} </a>
        </div>
        <div v-else class="coming-soon text-center">
            <h1>Próximamente más información</h1>
        </div>
    </div>
    <div v-if="props.day == 7" class="guest-details flex flex-col justify-center items-center">
        <div v-if="isSundayActive" class="text-center">
            <a :href="socialNetworkSaturday" target="_blank"> {{ socialNetworkSaturday }} </a>
        </div>
        <div v-else class="coming-soon text-center">
            <h1>?????????</h1>
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

    #dibujos_2x1 {
        width: 60%;
        position: relative;
        top: 55%; 
    }

    #owowa, #contentw-titulo {
        position: relative; 
        top: 55%;
        left: -10%;
        width: 60%;
    }

    #watchparty-titulo {
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

    #miercoles-container {
        background-image: url('../assets/miercoles/banner_2x1.png');
        max-width: 700px;
        max-height: 470px;
        width: 100%;
        height: auto;
        margin-bottom: 10px;
        aspect-ratio: 500 / 270;
    }

    #jueves-container {
        background-image: url('../assets/jueves/banner_jueves.png');
        max-width: 700px;
        max-height: 470px;
        width: 100%;
        height: auto;
        margin-bottom: 10px;
        aspect-ratio: 500 / 270;
    }

    #viernes-container {
        background-image: url('../assets/viernes/bannerv.png');
        max-width: 700px;
        max-height: 470px;
        width: 100%;
        height: auto;
        margin-bottom: 10px;
        aspect-ratio: 500 / 270;
    }

    #sabado-container {
        background-image: url('../assets/sabado/banner.png');
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

    .vtuber-wednesday-icon-first-row {
        max-width: 33%;
        height: auto;
        width: 100%;
    }

    .vtuber-thursday-icon-first-row, .vtuber-thursday-rtext-second-row {
        max-width: 24%;
        height: auto;
        width: 100%;
        margin-right: 3%;
    }

    .vtuber-friday-icon-first-row {
        max-width: 35%;
        height: auto;
        width: 100%;
    }

    .vtuber-thursday-rtext-second-row {
        max-width: 30%;
    }
    

    .vtuber-thursday-icon-first-row {
        position: relative;
        top: 1.2vw;
    }

    .vtuber-thursday-pupa-icon-first-row {
        position: relative;
        top: 1vw;
    }


    .vtuber-thursday-pupa-icon-first-row, .vtuber-thursday-ptext-second-row {
        max-width: 33%;
        height: auto;
        width: 100%;
        margin-right: 3%;
    }

    .vtuber-thursday-ptext-second-row {
        max-width: 28%;
        position: relative;
        left: -4%;
    }

    .vtuber-friday-rtext-second-row, .vtuber-friday-ntext-second-row {
        max-width: 33%;
        height: auto;
        width: 100%;
        margin-right: 3%;
    }

    .vtuber-saturday-icon-first-row {
        max-width: 25%;
        height: auto;
        width: 100%;
        margin-right: 4%;
    }

    .vtuber-saturday-icon-first-row-last {
        margin-right: 0% !important;
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

    @media (max-width: 1440px) {
        
        .vtuber-thursday-icon-first-row {
            position: relative;
            top: 2.5vw;
        }
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