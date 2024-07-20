<script setup>
const props = defineProps(['imgSrc','link'])
</script>
<template>
    <div class="guest-details flex flex-col justify-center items-center">
        <img style="width:400px" :src="imgSrc">
        <div class="-rotate-3">
        <a href="link">{{ link }}</a>
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
</style>