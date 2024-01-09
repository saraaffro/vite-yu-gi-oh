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
    <h2>Filtra per Archetype</h2>
    <select v-model="store.searchText" @change="$emit('filter')">
        <option value="" selected>Filtra Archetype</option>
        <option v-for="(type, i) in store.archList" :key="i" :value="type.archetype_name">{{ type.archetype_name
        }}</option>
    </select>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

h2 {
    margin: 5px 10px;
}

select {
    margin-left: 10px;
    background-color: $main-color;
}
</style>