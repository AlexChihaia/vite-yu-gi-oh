<script>
import axios from 'axios';
import AppCardHeader from './CardHeaderComponent.vue';
import AppSelect from './SelectComponent.vue';
import { store } from '../store';
export default {
    name: 'AppCards',
    components: {
        AppCardHeader,
        AppSelect,
    },
    data() {
        return {
            store,
        }
    },
    methods: {
        cardSearch() {

            if (store.selectedArchetype === '') {
                axios.get(store.apiURL + '?num=20&offset=0').then((response) => {
                    store.cards = response.data.data;
                })

            } else {
                axios.get(store.apiURL + '?archetype=' + store.selectedArchetype + '&num=20&offset=0').then((response) => {
                    store.cards = response.data.data;
                })

            }

        }
    },
    created() {
        this.cardSearch();
    },
};






</script>
<template>
    <div class="container py-4">
        <AppSelect @archetypeSelection="cardSearch" />
        <ul class="row bg-white px-5 py-5 justify-content-center">
            <AppCardHeader />
            <li v-for="card in store.cards" class="col-2 mx-3 mb-5 px-0">
                <img :src="card.card_images[0].image_url" alt="">

                <h5>{{ card.name }}</h5>
                <p>{{ card.archetype }}</p>
            </li>

        </ul>
    </div>
</template>
<style scoped>
* {
    list-style: none;
}

li {
    background-color: #d48f38;
}

img {
    width: 100%;
    display: block;
}
</style>
