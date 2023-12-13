<script>
import AppSelect from './sub_components/SelectComponent.vue';
import AppCards from './sub_components/CardsComponent.vue';
export default {
    name: 'AppMain',
    components: {
        AppSelect,
        AppCards,
    }
};
</script>
<template>
    <div class="container py-4">
        <AppSelect />

        <AppCards />
    </div>
</template>
<style scoped></style>