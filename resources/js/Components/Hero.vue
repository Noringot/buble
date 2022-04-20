<template>
        <section class="hero">
            <div class="container">
                <div class="hero__top flex justify-between">
                    <div class="hero__text hero__text-left">New collection</div>
                    <h1 class="hero__title">Bubble Drop</h1>
                    <div class="hero__text hero__text-right text-uppercase">PUSHKEEN & BACK TO THE ROOTS</div>
                </div>
                <div class="hero__bottom flex justify-between">
                    <div class="hero__subtitle">Рассмотрим основные развивающиеся тренды 2022 года в моушн дизайне. </div>
                    <div class="hero__nft">
                        <img src="images/binance.png" alt="" class="hero__nft-image">
                        <div class="hero__nft-token">428 tokens</div>
                    </div>
                </div>
            </div>
        </section>
</template>

<script>

export default {
    name: "Index",
}
</script>

<style scoped>

.hero {
    background: url('/images/hero-bg.png') no-repeat center -5%;
    overflow: hidden;
}

.hero__top {
    margin-bottom: 150px;
}

.hero__text {
    font-size: 22px;
    color: var(--add-color);
    text-transform: uppercase;
    writing-mode: tb-rl;
}
.hero__text-left {
    transform: rotateZ(180deg);
    text-align: end;
}
.hero__title {
    font-family: 'TippyToesBold';
    font-size: 150px;
    font-weight: 700;
    color: #FFF;
    display: flex;
    align-items: center;
}
.hero__subtitle {
    font-size: 16px;
    max-width: 250px;
}
.hero__nft {
    display: flex;
    align-items: center;
}

.hero__nft-token {
    color: var(--add-color);
    margin-left: 30px;
    text-transform: uppercase;
    position: relative;
    z-index: 5;
}
.hero__nft-token:before {
    content: '';
    position: absolute;
    height: 44px;
    width: 600px;
    top: 100%;
    left: -14px;
    background-color: #272727;
    transform: translateY(-33px);
    z-index: -1;
}

</style>
