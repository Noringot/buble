<template>
    <div class="employees">
        <div class="container">
            <div class="employees__buttons">
                <button class="employees__button employees__rare active" @click.prevent="changeRare">Редкие</button>
                <button class="employees__button employees__veryrare" @click.prevent="changeRare">Очень редкие</button>
            </div>
                <swiper
                    :modules="modules"
                    slides-per-view="auto"
                    :loopedSlides="2"
                    :space-between="40"
                    navigation
                    :slideToClickedSlide="true"
                    :centeredSlides="true"
                    class="slider"
                    loop
                    @slideChange="setOptionsActiveSlide"
                    @init="enableSideShadow"
                >
                    <swiper-slide style="width: auto;" v-for="(slide, index) in slides" :key="index" class="slide" :data-id="slide.id">
                        <div class="slide__image">
                            <img :src="'/images/' + slide.veryRareImage" alt="" v-if="isVeryRare">
                            <img :src="'/images/' + slide.image" alt="" v-else>
                        </div>
                        <div class="slide__name">
                            {{ slide.name }}
                        </div>
                        <div class="slide__title">
                            «{{ slide.title }}»
                        </div>
                    </swiper-slide>
                </swiper>
            <div class="employees__article" v-if="articles[activeSlideId]">
                <div class="employees__description">
                    <div class="employees__quotes">бб</div>
                    <div class="employees__text">
                        {{ articles[activeSlideId].description }}
                    </div>
                    <div class="employees__quotes employees__quotes-reverse">бб</div>
                </div>
                <div class="employees__person">
                    <div class="employees__label">
                        <div class="employees__token">60 tokens</div>
                        <div class="employees__link">{{ articles[activeSlideId].link }}</div>
                    </div>
                    <div class="employees__image">
                        <img :src="'/images/' + articles[activeSlideId].image" alt="">
                    </div>
                </div>
            </div>
            </div>
        </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation } from 'swiper';
import 'swiper/css';

export default {
    name: "Slider",
    components: {
        Swiper,
        SwiperSlide,
    },
    setup() {
        return {
            modules: [Navigation],
        };
    },
    data() {
        return {
            activeSlideId: 0,
            isVeryRare: false,
            slides: [
                {id: 0, image: 'slider-img-rare-1.png', veryRareImage: 'slider-img-veryrare-1.png', name: 'Елена денисова', title: 'bub1'},
                {id: 1, image: 'slider-img-rare-2.png', veryRareImage: 'slider-img-veryrare-2.png', name: 'Света Белая', title: 'bub2'},
                {id: 2, image: 'slider-img-rare-3.png', veryRareImage: 'slider-img-veryrare-3.png', name: 'Надя Авдеева', title: 'bub3'},
                {id: 3, image: 'slider-img-rare-4.png', veryRareImage: 'slider-img-veryrare-4.png', name: 'Макс Кулагин', title: 'bub4'},
            ],
            articles: [
                {
                    image: 'slider-avatar-1.png',
                    description: 'Фрилансер моушн дизайнер, иллюстратор и энтузиаст Бэн Марриот из Сиднея собирает классные свежие подборки анимационных работ. У него хороший вкус и выбранные ним работы точно вдохновят вас на что-то клёвое. От рекламных роликов до снимков продукта, маркетинговых кампаний и дизайна игр, используя возможности 3D открываются новые двери для отображения картин.',
                    link: '@elena'
                },
                {
                    image: 'slider-avatar-2.png',
                    description: 'Если в последние 12 месяцев Вы находились рядом с технически подкованным другом или родственником, есть большая вероятность того, что в какой-то момент Вы слышали упоминание о виртуальной реальности. Виртуальная реальность неуклонно возрастала от амбициозной фантазии, ориентированной на игры, еще в 2012 году, до реальной среды.',
                    link: '@sveta'
                },
                {
                    image: 'slider-avatar-3.png',
                    description: 'Благодаря их малым масштабам и широкой доступности, gif являются отличным способом привлечь клиентов и поделиться идеями, особенно в социальных сетях. GIF могут быть еще больше использованы компаниями, которые хотят продавать себя в цифровом пространстве.\n',
                    link: '@nadya'
                },
                {
                    image: 'slider-avatar-4.png',
                    description: 'Использование визуальных эффектов в рекламных роликах позволило компаниям продвигать презентацию своих продуктов. А это является важным аспектом для любой маркетинговой кампании. От улучшения деталей и эстетики, которые способствуют построению более красивой картинки до повышения драматических моментов и увеличения общего эффекта от рекламы.',
                    link: '@max'
                },
            ]
        }
    },
    methods: {
        setOptionsActiveSlide() {
            setTimeout(() => {
                const slides = document.querySelectorAll('.swiper-slide');
                slides.forEach(slide => {
                    slide.children[1].style.cssText = 'color: var(--main-color);';
                    slide.children[2].style.cssText = 'opacity: 0; display: none;';
                })

                const activeSlide = document.querySelector('.swiper-slide-active');
                this.activeSlideId =activeSlide.dataset.id
                if(activeSlide) {
                    const activeSlideName = activeSlide.children[1];
                    const activeSlideTitle = activeSlide.children[2];

                    activeSlideName.style.cssText = 'color: var(--add-color);'
                    activeSlideTitle.style.cssText = 'opacity: 1; display: block;';
                }
            }, 100)
        },
        enableSideShadow() {
            const swiper = document.querySelector('.swiper');
            const leftSideShadow = document.createElement('div');
            const rightSideShadow = document.createElement('div');

            leftSideShadow.classList.add('employees__shadow', 'employees__shadow-left');
            rightSideShadow.classList.add('employees__shadow', 'employees__shadow-right');

            swiper.append(leftSideShadow);
            swiper.append(rightSideShadow);

        },
        changeRare(ev) {
            const buttons = Array.from(document.querySelectorAll('.employees__button'));
            buttons.forEach(button => {
                button.classList.remove('active');
            });
            ev.target.classList.add('active');
            this.isVeryRare = ev.target.classList.contains('employees__veryrare');
        },
    },
}
</script>

<style scoped>


.slider {
    padding-bottom: 60px;
}

.slide__image img {
    width: 100%
}

.slide__image {
    width: 337px;
    height: 200px;
    margin-bottom: 40px;
}

.slide__name {
    color: var(--main-color);
    font-size: 24px;
    font-weight: 700;
    text-align: center;
    margin-bottom: 20px;
    text-transform: uppercase;
    transition: .3s color ease ;
}

.slide__title {
    color: #FFF;
    font-family: 'TippyToesBold';
    font-size: 50px;
    text-align: center;
    transition: .3s opacity ease;
    display: none;
}

.employees {
    padding: 80px 0;
    position: relative;
}

.employees__article {
    display: flex;
    margin-top: 20px;
}

.employees__description {
    margin-right: 90px;
}

.employees__text {
    font-size: 18px;
    line-height: 26px;
}

.employees__quotes {
    font-family: 'TippytoesXTraBold';
    font-weight: 700;
    font-size: 40px;
    color: #FFFFFF;
}
.employees__quotes-reverse {
    transform: rotateZ(180deg);
}

.employees__label {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-right: 15px;
}

.employees__token {
    display: flex;
    align-items: flex-end;
    font-weight: 700;
    font-size: 30px;
    text-transform: uppercase;
    color: #2D2D2D;
    writing-mode: tb-rl;
    transform: rotateZ(180deg);
}

.employees__link {
    font-family: 'TippytoesXTraBold';
    font-weight: 700;
    font-size: 22px;
    color: #FFFFFF;
}

.employees__person {
    flex: 1 0 auto;
    display: flex;
}

.employees__image img {
    width: 100%;
    object-fit: cover;
}

.employees__buttons {
    text-align: center;
    margin-bottom: 40px;
}

.employees__button {
    color: var(--add-color);
    font-size: 18px;
    font-weight: 600;
    padding: 15px 45px;
    letter-spacing: 0.02em;
    border: 1px solid var(--add-color);
    transition: .2s all ease;
}

.employees__button:first-child {
    margin-right: 22px;
}

.employees__button.active {
    background-color: var(--add-color);
    color: #000;
}

</style>
