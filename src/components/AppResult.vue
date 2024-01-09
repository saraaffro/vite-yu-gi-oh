<script >
// importo store
import { store } from '../store';

export default {
    name: 'AppResult',
    data() {
        return {
            store,
        }
    },
    computed: {
        resultCard() {
            return store.cardList.length;
        }
    }
}
</script>

<template>
    <div class="found-cards" v-if="resultCard > 0">Sono state trovate {{ resultCard }} carte</div>
    <div class="found-cards" v-else>Non sono state trovate carte</div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.found-cards {
    margin: 10px;
    color: $main-color;
}
</style>