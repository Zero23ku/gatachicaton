<script setup>
    import { reactive, onMounted, onUnmounted } from 'vue';
    import VtuberInfo from './components/VtuberInfo.vue'
    import peo from './assets/peo.wav'
    let keyList = []
    let intervalId = null
    const kCode = ['ArrowUp', 'ArrowUp', 'ArrowDown', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'ArrowLeft', 'ArrowRight', 'b', 'a', 'Enter']

    const sound = new Audio(peo)

    const vtuberData = reactive({
        day: 0
    })

    const renderGuests = true;
    let activeDay = 0

    function selectDay(day) {
        vtuberData.day = day
        activeDay = day
    }

    function clearKeyList() {
        keyList = []
    }

    function isCodeValid() {
        if( (keyList.length === kCode.length) && keyList[0] === kCode[0] && keyList[1] == kCode[1] &&  keyList[2] === kCode[2] &&
            keyList[3] === kCode[3] && keyList[4] === kCode[4] && keyList[5] === kCode[5] && keyList[6] === kCode[6] && keyList[7] === kCode[7] && 
            keyList[8].toLowerCase() === kCode[8] && keyList[9].toLowerCase() === kCode[9] && keyList[10] === kCode[10]  ) {
            
            return true
        }

        return false


    }


    onMounted(() => {
        console.log("Que mirai guaton feo culiao y la conchetumare")
        window.addEventListener('keydown', (event) => {
            clearInterval(intervalId)
            keyList.push(event.key)
            if(event.key === 'Enter' && isCodeValid()) {
                sound.play()
            }else if(event.key === 'Enter'){
                clearKeyList()
            }
            intervalId = setInterval(clearKeyList, 3000)
            
        });

        intervalId = setInterval(clearKeyList, 3000)
        onUnmounted(() => {
            clearInterval(intervalId)
        })
    })
</script>

<template>
    <div class="bg-container" @keydown="handleKeyDown(e)">
        <header>
            <div class="header-container">
                <div class="menu grid grid-cols-3 gap-4 content-center text-center">
                    <div><a href="#about">Sobre el evento</a></div>
                    <div><a href="#guests">Actividades</a></div>
                    <div><a href="#helpus">Apoya la causa</a></div>
                </div>
                <div class="logo-container">
                    <div class="flex justify-center items-center">
                        <img class="logo" src="./assets/logomock.png"></img>
                    </div>
                    <div class="text-container">
                        <h1 class="content-center text-center">Gatachicaton</h1>
                        <h2 class="content-center text-center ">Del Lunes 5 al Domingo 11 de Agosto</h2>
                        <h2 class="content-center text-center -rotate-3 grow"><a href="https://twitch.tv/retniuwu">twitch.tv/retniuwu</a></h2>
                        
                    </div>
                </div>
                
            </div>
        </header>
        <div id="about" class="body-container">
            <div class="img-container flex justify-center">
                <img src="./assets/gatachica.webp"></img>
            </div>
            <div class="text-container">
                <p>
                    Ella es sombra, mas conocida como "la gata chica". Tiene 6 meses de edad y sufre de una displacía de cadera bilateral producida por una artrosis congénita, por lo que necesita ser intervenida quirúrgicamente en ambas patas traseras.
                    Este evento tiene como único fin reunir fondos para ayudar a amortiguar el costo de las cirugías necesarias y tratamientos post operatorios de Sombra, que a día de hoy ascienden a 850 usd aproximadamente.
                </p>
            </div>
        </div>
        <div id="helpus" class="body-container donation-container mb-28">
            <h1 class="content-center text-center">GRACIAS POR AYUDAR</h1>
            <div class="flex flex-col justify-center items-center">
                <p style="font-size: 1.5rem; line-height: 2rem;">Se consiguió el 39.8% de la meta :D</p>
                <p style="font-size: 1.5rem; line-height: 2rem;">Aún puedes ayudar donando a través de</p>
                <a href="https://esponsor.com/retniuwu"><img src="./assets/esponsor_logo.svg"/></a>
            </div>
        </div>

        <div id="guests" class="body-container guest-container">
            <h1 class="content-center text-center">Actividades</h1>
            <div v-if="renderGuests" class="grid grid-col-2 gap-4">
                <div id="guestsDay" class="flex flex-col items-center justify-center">
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 1}"><a @click="selectDay(1)" class=""><h2 class="line-through">Lunes</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 2}"><a @click="selectDay(2)" class=""><h2 class="line-through">Martes</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 3}"><a @click="selectDay(3)" class=""><h2 class="line-through">Miércoles</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 4}"><a @click="selectDay(4)" class=""><h2 class="line-through">Jueves</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 5}"><a @click="selectDay(5)" class=""><h2 class="line-through">Viernes</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 6}"><a @click="selectDay(6)" class=""><h2 class="line-through">Sabado</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 7}"><a @click="selectDay(7)" class=""><h2 class="line-through">Domingo</h2></a></div>
                </div>
                <VtuberInfo :day="vtuberData.day"/>
    
            </div>
        </div>
        
        <footer>
            <div class="flex flex-col justify-center items-center">
                <p>Creado por <a href="https://twitter.com/harpuiavt">Harpuia 🐸</a></p>
            </div>
        </footer>
    </div>
</template>

<style scoped>

    .animation {
        transition: all .2s ease-in-out; 
    }
    

    .grow { 
        transition: all .2s ease-in-out; 
    }

    .grow:hover { 
        transform: scale(1.1); 
    }

    #guestsDay h2 {
        font-size: 30px !important;
    }

    #guests h1, #helpus h1 {
        font-size: 4.3vw;
    }
    
    .donations-content {
        text-align: center;
    }

    .activeDay {
        transform: rotate(45deg);
    }

    @media (max-width: 768px) {
        
        #guests h1, #helpus h1 {
            font-size: 10vw;
        }   
    }

    

</style>
