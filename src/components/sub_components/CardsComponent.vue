<script>
import axios from 'axios';
import AppCardHeader from './CardHeaderComponent.vue';
export default {
    name: 'AppCards',
    components: {
        AppCardHeader,
    },

    data() {
        return {
            cards: [],
            apiURL: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
        }
    },
    created() {
        axios.get(this.apiURL).then((data) => {
            console.log(data);
            this.cards = data.data.data;
        });
    },
}
</script>
<template>
    <div class="container py-4">
        <AppCardHeader />
        <ul class="row bg-white px-5 py-5">
            <li v-for="card in cards" class="col-2 mx-3 my-3 px-0">
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