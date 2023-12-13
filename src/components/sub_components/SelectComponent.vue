<script>
export default {
    name: 'AppSelect',
}
</script>
<template>
    <div class="col-2">
        <label class="visually-hidden" for="autoSizingSelect">Preference</label>
        <select class="form-select" id="autoSizingSelect">
            <option selected>Select Filter</option>
            <option value="Alien">Alien</option>
            <option value="Ancient Warriors">Ancient Warriors</option>
            <option value="Draconia">Draconia</option>
        </select>
    </div>
</template>
<style scoped></style>