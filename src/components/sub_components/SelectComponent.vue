<script>
import axios from 'axios';
import { store } from '../store';
export default {
    name: 'AppSelect',
    emits: ['archetypeSelection'],
    data() {
        return {
            store,
        };
    },
    created() {
        axios.get(store.apiArchetypesURL).then((response) => {
            store.archetypes = response.data;
        })
    },
}
</script>
<template>
    <label class="visually-hidden" for="archetype-selector">Select Archetype</label>
    <select class="form-select col-1" name="archetype" id="archetype-selector" v-model="store.selectedArchetype"
        @change="$emit('archetypeSelection')">
        <option selected value="">Select Archetype...</option>
        <option v-for="archetype in store.archetypes" :value="archetype.archetype_name">{{ archetype.archetype_name }}
        </option>

    </select>
</template>
<style scoped></style>