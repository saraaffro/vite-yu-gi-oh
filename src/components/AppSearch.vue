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
    <select v-model="store.searchText" @change="$emit('filter')">
        <option value="" selected>Filtra Archetype</option>
        <option v-for="(type, i) in store.archList" :key="i" :value="type.archetype_name">{{ type.archetype_name
        }}</option>
    </select>
</template>

<style lang="scss" scoped></style>