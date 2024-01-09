<script >
// importo store
import { store } from '../store';

export default {
    name: 'AppSearch',
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <!-- <input type="text" placeholder="Cerca carta" v-model="store.searchText">
    <button type="submit" @click.prevent="$emit('search')">cerca</button>
    <button type="reset">reset</button> -->

    <select>
        <option value="" selected>Filtra Archetype</option>
        <option value="" v-for="(type, i) in store.optionApiURL">{{ type.archetype_name }}</option>
    </select>
</template>

<style lang="scss" scoped></style>