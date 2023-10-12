<template>
    <swiper :autoplay="{
        delay: 2500,
        disableOnInteraction: false,}"
        :pagination="{
        clickable: true,}"
        :navigation="true" :modules="modules" class="swiper swiper">

        <div class="swiper-wrapper swiper-wrapper">
            <swiper-slide v-for="(slide, index) in slides" :key="index" class="swiper-slide swiper-slide">
                <div class="solution__swiper">
                    <a :href="slide.link">
                        <img :src="slide.imageSrc" :alt="slide.imageAlt" />
                    </a>
                </div>
            </swiper-slide>
        </div>
    </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';

import 'swiper/css';
import 'swiper/css/pagination';
import 'swiper/css/navigation';

import { Autoplay, Pagination, Navigation } from 'swiper/modules';

export default {
    name: 'solutionSwiper',

    components: {
        Swiper,
        SwiperSlide,
    },

    data() {
        return {
            products: [
                { title: 'DBMS', subtitle: 'DBMS Monitoring' },
                { title: 'APM', subtitle: 'APM Monitoring' },
                { title: '인공지능', subtitle: 'AI Vision' },
                { title: '클라우드', subtitle: 'Cloud' }
            ],

            slides: [
                {
                    imageSrc: 'https://wedatalab.com/wp-content/uploads/2023/04/Frame-31-4.png',
                    imageAlt: 'APM Monitoring'
                },
                {
                    imageSrc: 'https://wedatalab.com/wp-content/uploads/2023/04/Frame-27-3.png',
                    imageAlt: 'AI Vision'
                },
                {
                    imageSrc: 'https://wedatalab.com/wp-content/uploads/2023/04/Frame-29-2.png',
                    imageAlt: 'DBMS Monitoring'
                },
                {
                    imageSrc: 'https://wedatalab.com/wp-content/uploads/2023/04/Frame-30-3.png',
                    imageAlt: 'DBMS Audit'
                }
            ]
        }
    },

    setup() {
        return {
            modules: [Autoplay, Pagination, Navigation],
        };
    },


};
</script>

<style scoped>
.swiper-slide {
    width: 100vw;
}

.solution__swiper img {
    width: 100%;
    height: auto;
}

/* 화면 넘김 */
.swiper-button-next:after,
.swiper-rtl .swiper-button-prev:after {
    content: 'next';
}

.swiper-button-next:after,
.swiper-button-prev:after {
    font-family: swiper-icons;
    font-size: var(--swiper-navigation-size);
    text-transform: none !important;
    letter-spacing: 0;
    font-variant: initial;
    line-height: 1;
    color: white;
}

.swiper-button-next,
.swiper-button-prev {
    position: absolute;
    top: var(--swiper-navigation-top-offset, 50%);
    width: calc(var(--swiper-navigation-size)/ 44 * 27);
    height: var(--swiper-navigation-size);
    margin-top: calc(0px - (var(--swiper-navigation-size)/ 2));
    z-index: 10;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--swiper-navigation-color, var(--swiper-theme-color));
    margin: 2rem;
    --swiper-navigation-size: 25px;
}
</style>
