<script setup>
import CardComponent from './CardComponent.vue';

</script>

<template>
    <section>
        <div class="container">
            <hr>
            <div class="row mt-4 p-4">
                <CardComponent />
                <CardComponent />
                <CardComponent />
            </div>
            <hr>
        </div>
    </section>
</template>

<style scoped>
section {
    display: flex;
    align-items: center;
    padding: 20px;
    /* background: #81c0ee; */
    margin-top: 8%;
    opacity: 0.7;

}
</style>

<!-- <template>
    <section>

        <vue-slider :options="sliderOptions">
        </vue-slider>

        <div class="cards">

            <div v-for="card in cards" :key="card.id" class="card">

                <CardComponent />

            </div>

        </div>

    </section>
</template>
  
<script setup>
import VueSlider from 'vue-slider-component'

import CardComponent from './CardComponent.vue';

const cards = [
    { id: 1 }, { id: 2 }, { id: 3 }, { id: 4 }, { id: 5 }, { id: 6 }
]

const sliderOptions = {
  // ...
  slidesToShow: 3,
  slidesToScroll: 1,
  infinite: false,
  dots: true
}
</script>
  
<style scoped>
.cards {
    overflow: hidden;
}

.card {
    width: 100%;
}
</style> -->