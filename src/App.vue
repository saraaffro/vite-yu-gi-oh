<script>
// importo axios
import axios from 'axios';

// importo componenti
import AppHeader from './components/AppHeader.vue'
import ListItems from './components/ListItems.vue'

// importo store
import { store } from './store';


export default {
  components: {
    AppHeader,
    ListItems,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCard() {
      axios
        .get(store.apiURL)
        .then((res => {
          // console.log(res.data.data);
          store.cardList = res.data.data;
        }))
        .catch((err) => {
          console.log("errori", err);
        })
    }
  },
  created() {
    this.getCard();
  }
}
</script>

<template>
  <AppHeader />
  <main>
    <div class="container">
      <ListItems />
    </div>

  </main>
</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use './styles/partials/variables' as *;

main {
  padding: 120px 0 50px;
  background-color: $main-color;

  .container {
    width: 80%;
    margin: 0 auto;
    background-color: white;
    padding: 20px;
  }
}
</style>
