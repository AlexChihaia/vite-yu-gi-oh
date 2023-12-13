<script >
import AppHeader from './components/HeaderComponent.vue';
import AppMain from './components/MainComponent.vue';

export default {

    components: {
        AppHeader,
        AppMain
    },
};
</script>

<template>
    <AppHeader />
    <div class="ac-container">
        <AppMain />
    </div>
</template>

<style scoped lang="scss">
.ac-container {
    width: 100%;
    background-color: #d48f38;
}
</style>
