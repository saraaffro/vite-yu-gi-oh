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
      let archURL = store.optionApiURL;

      if (store.searchText !== '') {
        if (myURL.includes('?')) {
          // se l'URL già contiene ?, aggiungo & e il nuovo parametro
          myURL += `&${store.archParam}=${store.searchText}`;
        } else {
          // Se l'URL non contiene ancora parametri, aggiungi ? seguito dal nuovo parametro
          myURL += `?${store.archParam}=${store.searchText}`;
        }

      }

      // chiamata api cards
      axios
        .get(myURL)
        .then((res => {
          // console.log(res.data.data);
          store.cardList = res.data.data;
        }))
        .catch((err) => {
          console.log("errori", err);
        })

      // chiamata api archetype
      axios
        .get(archURL)
        .then((res => {
          // console.log(res.data);
          store.archList = res.data;
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
      <AppSearch @filter="getCard" />
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
