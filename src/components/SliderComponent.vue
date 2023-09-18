<script setup>
import CardComponent from './CardComponent.vue';
import VueAIcarousel from 'vue-ai-carousel'

const cards = [
    { id: 1 }, { id: 2 }, { id: 3 }, { id: 4 }, { id: 5 }, { id: 6 }
]
</script>

<template>
    <section>
        <div class="container">
            <hr>
            <div class="container row mt-4 p-4 col-8">
                <VueAIcarousel :Property="{ ID: 'Unique_id', Dlay: 1000 }" :options="{ itemsPerSlide: 3, loop: true }">
                    <CardComponent v-for="card in cards" :key="card.id" />
                </VueAIcarousel>
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

.row {
    margin-left: 15%;
}

</style>