<script>
// importo axios
import axios from 'axios';

// importo componenti
import AppHeader from './components/AppHeader.vue'
import ListItems from './components/ListItems.vue'
import AppSearch from './components/AppSearch.vue'

// importo store
import { store } from './store';


export default {
  components: {
    AppHeader,
    ListItems,
    AppSearch
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCard() {
      let myURL = store.apiURL;

      axios
        .get(myURL)
        .then((res => {
          // console.log(res.data.data);
          store.cardList = res.data.data;
        }))
        .catch((err) => {
          console.log("errori", err);
        })

      axios
        .get(store.optionApiURL)
        .then((res => {
          console.log(res.data);
          store.optionApiURL = res.data;
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
      <AppSearch />
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
