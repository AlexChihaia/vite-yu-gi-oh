<script>
import axios from 'axios';
export default {
    name: 'AppCardHeader',

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

};
</script>
<template>
    <div class="container">
        <h6>Found {{ cards.length }} cards</h6>
    </div>
</template>
<style scoped>
div {
    height: 55px;
}
</style>