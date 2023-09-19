<script setup>
import CardComponent from './CardComponent.vue';
import { Swiper, SwiperSlide } from 'swiper/vue';

// const cards = [
//     { id: 1 }, { id: 2 }, { id: 3 }, { id: 4 }, { id: 5 }, { id: 6 }, { id: 7 }
// ]
</script>

<template>
    <section>
        <div class="container">
            <hr>

            <swiper :modules="modules" :slides-per-view="3" :space-between="50" :pagination="{ clickable: true }"
                :scrollbar="{ draggable: true }" @swiper="onSwiper" @slideChange="onSlideChange">
                <div class="row">
                    <swiper-slide>
                        <CardComponent />
                        <CardComponent />
                        <CardComponent />
                    </swiper-slide>
                </div>
            </swiper>

            <!-- <CardComponent />
                <CardComponent /> -->

        </div>
    </section>
</template>

<style scoped>
section {
    display: flex;
    align-items: center;
    padding: 20px;
    /* background: #81c0ee; */
    margin-top: 4%;
    opacity: 0.7;

}
</style>