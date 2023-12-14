<script>
import { store } from '../store';
export default {
    name: 'AppCardHeader',

    data() {
        return {
            store
        }
    },
    computed: {
        cardsFound() {
            return store.cards.length;
        },
    },

};
</script>
<template>
    <div class="container d-flex align-items-center">
        <h6>Found {{ cardsFound }} cards</h6>
    </div>
</template>
<style scoped>
div {
    height: 55px;
    background-color: black;

    h6 {
        color: white;
    }
}
</style>