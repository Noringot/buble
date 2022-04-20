<template>
    <section class="about">
        <div class="container">
            <div class="about__content">
                <h6 class="about__title">О проекте</h6>
                <div class="about__text">Затронем тенденции, начиная с фильмов и коммерческой рекламы, до тематических исследований и всего, что между ними. Вы не увидели бы эту статью без бесчисленных вкладов.</div>
                <div class="about__img">
                    <img src="images/gq.png" alt="GQ">
                </div>
                <a href="#" class="about__link">Читать больше в статье </a>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "About"
}
</script>

<style scoped>
.about {
    background-image: url('../../images/pam.png'), linear-gradient(180deg, rgba(0,0,0,1) 0%, rgba(249,249,249,0) 32%);
    background-repeat: no-repeat;
    background-position: right 0;
    background-color: rgba(0,0,0, 0.4);
    overflow: visible;
    padding: 100px;
}
.about__content {
    max-width: 50%;
}
.about__title {
    color: var(--add-color);
    text-transform: uppercase;
    font-size: 30px;
    font-weight: 600;
    margin-bottom: 13px;
    letter-spacing: 0.02em;
}
.about__text {
    line-height: 26px;
    margin-bottom: 26px;
}
.about__link {
    margin-top: 11px;
    color: #FFF;
    position: relative;
    display: inline-block;
    /*text-decoration: underline;*/
}
.about__link:before {
    content: '';
    position: absolute;
    width: 100%;
    height: 1px;
    background-color: #FFF;
    top: 100%;
}

</style>
