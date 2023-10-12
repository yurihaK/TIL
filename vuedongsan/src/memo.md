<template>
    <section class="client-container">
        <p class="client__title">
            Our clients
        </p>
                <swiper
            :slidesPerView="5" :slidesGroup="5" :spaceBetween="30" :loop="true" :autoplay="{
            delay: 2500,
            disableOnInteraction: false,}"
            :modules="modules"
            class="swiper client-swiper">

            <swiper-slide v-for="item in clients" :key="item.title" class="swiper-slide book-swiper-slide">
                <div class="book__swiper">
                    <a href="#" class="book__swiper-a">
                        <img :src="item.url" :alt="item.title" class="book__swiper-img">
                    </a>
                </div>
            </swiper-slide>
        </swiper>
    </section>
</template>

<script>

import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import { Autoplay } from 'swiper/modules';


export default {
    name: 'ClientSwiper',

    components: {
        Swiper,
        SwiperSlide,
    },

    data() {
        return {
            clients: []
        }
    },

    mounted() {
        fetch("/json/clients.json")
            .then(response => response.json())
            .then(data => {
                this.clients = data;
            })
            .catch(error => console.error("Error loading JSON:", error));
    },

    setup() {
        return {
            modules: [Autoplay],
        };
    },
};

</script>



<style scoped>
</style>