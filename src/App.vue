<script setup>
    import { reactive } from 'vue';
    import VtuberInfo from './components/VtuberInfo.vue'
    import vtuber_mock from './assets/vtuber_mock.png'

    const vtuberData = reactive({
        imgSrc: '',
        link: ''
    })

    const renderGuests = false;

    function selectVtuber(vtuber) {
        switch(vtuber) {
            case 1:
            console.log(vtuber);
                vtuberData.imgSrc = vtuber_mock
                vtuberData.link = 'https://twitch.tv/test1'
                break;
            case 2:
                console.log(vtuber);
                vtuberData.imgSrc = vtuber_mock
                vtuberData.link = 'https://twitch.tv/test2'
                break;
            case 3:
                console.log(vtuber);
                vtuberData.imgSrc = vtuber_mock
                vtuberData.link = 'https://twitch.tv/test3'
                break;
            case 4:
                console.log(vtuber);
                vtuberData.imgSrc = vtuber_mock
                vtuberData.link = 'https://twitch.tv/test4'
                break;
            case 5:
                console.log(vtuber);
                vtuberData.imgSrc = vtuber_mock
                vtuberData.link = 'https://twitch.tv/test5'
                break;
        }
    }
</script>

<template>
    <div class="bg-container">
        <header>
            <div class="header-container">
                <div class="menu grid grid-cols-3 gap-4 content-center text-center">
                    <div><a href="#about">Sobre el evento</a></div>
                    <div><a href="#guests">Invitados</a></div>
                    <div><a href="#helpus">Apoya la causa</a></div>
                </div>
                <div class="logo-container">
                    <div class="flex justify-center items-center">
                        <img class="logo" src="./assets/logomock.png"></img>
                    </div>
                    <div class="text-container">
                        <h1 class="content-center text-center">Gatachicaton</h1>
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
            <h1 class="content-center text-center">Invitados</h1>
            <div v-if="renderGuests" class="grid grid-cols-2 gap-4">
                <div class="flex flex-col items-center">

                    <div class="mb-2"><a @click="selectVtuber(1)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                    <div class="mb-2"><a @click="selectVtuber(2)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                    <div class="mb-2"><a @click="selectVtuber(3)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                    <div class="mb-2"><a @click="selectVtuber(4)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                    <div class="mb-2"><a @click="selectVtuber(5)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                </div>
                <VtuberInfo :imgSrc="vtuberData.imgSrc" :link="vtuberData.link"/>
     
            </div>
            <div v-else>
                <h1 class="content-center text-center coming-soon -rotate-3">Próximamente</h1>
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
    

    .grow { 
        transition: all .2s ease-in-out; 
    }

    .grow:hover { 
        transform: scale(1.1); 
    }

    

</style>
