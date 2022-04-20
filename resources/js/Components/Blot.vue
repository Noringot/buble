<template>
    <section class="blot">
        <div class="blot__wrapper flex justify-around">
            <div class="blot__image" v-for="image in blotsArray">
                <img :src="'/images/' + image" alt="">
            </div>
        </div>
        <div class="blot__shadow blot__shadow-left"></div>
        <div class="blot__shadow blot__shadow-right"></div>
    </section>
</template>

<script>
export default {
    name: "Blot",
    data() {
        return {
            blotsArray: [
                'blot-1.png',
                'blot-2.png',
                'blot-3.png',
                'blot-4.png',
                'blot-5.png'
            ]
        }
    }
}
</script>

<style scoped>
.blot {
    padding: 120px 120px;
    background-color: #000;
    position: relative;
}
.blot__shadow {
    position: absolute;
    top: 0;
    width: 200px;
    height: 100%;
    background: rgb(0,0,0);
    background: linear-gradient(90deg, rgba(0,0,0,1) 17%, rgba(0,0,0,0.7007003484987745) 54%, rgba(249,249,249,0) 100%);
}
.blot__shadow-left {
    left: 100px;
}
.blot__shadow-right {
    transform: rotateZ(180deg);
    right: 100px;
}
</style>
