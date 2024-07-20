<script setup>
    import { reactive, ref } from 'vue';
    import VtuberInfo from './components/VtuberInfo.vue'
    import vtuber_mock from '@/assets/vtuber_mock.png'

    const vtuberData = reactive({
        imgSrc: '',
        link: ''
    })

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
                        <h2 class="content-center text-center -rotate-3"><a href="https://twitch.tv/retniuwu">twitch.tv/retniuwu</a></h2>
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
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque nec efficitur nunc. In bibendum nisl mi, a maximus leo commodo at. Ut velit massa, dictum ut blandit a, sagittis in purus. Vivamus eu urna vitae nisl aliquam gravida. Aenean porta, quam et porta iaculis, eros orci lacinia nunc, sit amet laoreet nibh lorem in diam. Quisque sollicitudin lacus et dignissim semper. Aenean pharetra arcu in libero pharetra aliquet.
                    Phasellus vel iaculis tellus. Nulla non eros consectetur, porta libero eu, sollicitudin libero. Nullam eu pretium magna. Sed sit amet faucibus sapien, ac faucibus quam. Fusce porttitor venenatis consequat. Etiam cursus, dolor ut pellentesque feugiat, ante lacus rhoncus nisl, at vestibulum nunc magna eu ex. Duis nec hendrerit tellus. Nulla semper leo ac lectus vehicula, non maximus metus rhoncus.
                </p>
            </div>
        </div>
        <div id="guests" class="body-container guest-container">
            <h1 class="content-center text-center">Invitados</h1>
            <div class="grid grid-cols-2 gap-4">
                <div class="flex flex-col items-center">

                    <div class="mb-2"><a @click="selectVtuber(1)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                    <div class="mb-2"><a @click="selectVtuber(2)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                    <div class="mb-2"><a @click="selectVtuber(3)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                    <div class="mb-2"><a @click="selectVtuber(4)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                    <div class="mb-2"><a @click="selectVtuber(5)" class=""><img src="./assets/guest_mock.jpeg"/></a></div>
                </div>
                <VtuberInfo :imgSrc="vtuberData.imgSrc" :link="vtuberData.link"/>
     
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

</style>
