<script setup>
    import { reactive } from 'vue';
    import VtuberInfo from './components/VtuberInfo.vue'

    const vtuberData = reactive({
        day: 0
    })

    const renderGuests = true;
    let activeDay = 0

    function selectDay(day) {
        vtuberData.day = day
        activeDay = day
    }
</script>

<template>
    <div class="bg-container">
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
                        <h2 class="content-center text-center ">Del Lunes 5 al Viernes 9 de Agosto</h2>
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
        <div id="guests" class="body-container guest-container">
            <h1 class="content-center text-center">Actividades</h1>
            <div v-if="renderGuests" class="grid grid-col-2 gap-4">
                <div id="guestsDay" class="flex flex-col items-center justify-center">
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 1}"><a @click="selectDay(1)" class=""><h2>Lunes</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 2}"><a @click="selectDay(2)" class=""><h2>Martes</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 3}"><a @click="selectDay(3)" class=""><h2>Miércoles</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 4}"><a @click="selectDay(4)" class=""><h2>Jueves</h2></a></div>
                    <div class="mb-2 cursor-pointer mx-10 animation" :class="{'-rotate-3': activeDay === 5}"><a @click="selectDay(5)" class=""><h2>Viernes</h2></a></div>
                </div>
                <VtuberInfo :day="vtuberData.day"/>
    
            </div>
        </div>
        <div id="helpus" class="body-container donation-container mb-28">
            <h1 class="content-center text-center">Donaciones</h1>
            <div class="donations-content flex flex-col justify-center items-center">
                <p>Apoya la causa donando por ESPONSOR</p>
                <a href="https://esponsor.com/retniuwu"><img src="./assets/esponsor_logo.svg"/></a>
            </div>
        </div>
        <footer>
            <div class="flex flex-col justify-center items-center">
                <p>Creado por <a href="https://twitter.com/harpuiavt">Harpuia 🐸</a></p>
            </div>"
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
