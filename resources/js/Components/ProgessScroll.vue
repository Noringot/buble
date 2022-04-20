<template>
    <div class="scroll">
        <div class="scroll__wrapper">
            <div class="scroll__block" :class="{active: num === numActiveBlock}" v-for="num in elementsNum" :key="num">
                <div class="scroll-line" v-if="num === numActiveBlock && num === elementsNum" style="margin: 0 auto 30px"></div>
                <button @click.prevent="() => {scrollToBlock(num)}" class="scroll__button">0{{ num }}</button>
                <div class="scroll-line" v-if="num === numActiveBlock && num !== elementsNum" style="margin: 30px auto 0"></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Scroll",
    data() {
        return {
            scrollTop: 0,
            numActiveBlock: 1,
            elementsNum: 3,
        }
    },
    methods: {
        scrollToBlock(numBlock) {
            if (numBlock === 1) {
                $('body, html').animate({scrollTop: 0+'px'}, 300);
            }
            if (numBlock === 2) {
                $('body, html').animate({scrollTop: 1212+'px'}, 300);
            }
            if (numBlock === 3) {
                $('body, html').animate({scrollTop: 2072+'px'}, 300);
            }
        }
    },
    mounted() {
        $(window).scroll(() => {
            this.scrollTop = $(window).scrollTop();
        })
    },
    watch: {
        scrollTop(newCoord) {
            if (newCoord >= 0 && newCoord < 950) {
                this.numActiveBlock = 1
            }
            if (newCoord >= 950 && newCoord < 1690) {
                this.numActiveBlock = 2
            }
            if (newCoord >= 1690) {
                this.numActiveBlock = 3
            }
        }
    }

}
</script>

<style scoped>

.scroll__wrapper {
    display: flex;
    flex-direction: column;
    font-family: 'TippytoesXTraBold';
    font-size: 35px;
    font-weight: 700;
}
.scroll-line {
    width: 1px;
    height: 90px;
    background: #2D2D2D;
    margin: 0 auto;
}
.scroll__block {
    font-weight: 700;
    font-size: 22px;
    margin-bottom: 30px;
    letter-spacing: 0.02em;
}
.active {
    color: var(--add-color);

}

</style>
