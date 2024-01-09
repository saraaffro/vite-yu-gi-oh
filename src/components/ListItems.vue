<script >
import SingleItem from '../components/SingleItem.vue'


// importo store
import { store } from '../store';

export default {
    name: 'ListItems',
    components: {
        SingleItem,
    },
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div class="row">
        <a href="#" class="card" v-for="card in store.cardList" :key="card.id">
            <SingleItem :info="card" />
        </a>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.row {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;

    .card {
        flex-basis: calc((100% / 5) - 20px);
        margin: 10px;
        background-color: $main-color;
    }
}
</style>