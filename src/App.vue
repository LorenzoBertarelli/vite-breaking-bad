<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store';
import SerchBar from './components/SerchBar.vue';

export default {
  components: {
    AppHeader,
    AppMain,
    SerchBar
},
  data () {
    return {
      store
    }
  },
  mounted() {
    store.loading = true;
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
          .then((resp) => {
            this.store.links = resp.data.data;
            this.store.loading = false;
          }) .catch ((error) => {
            this.store.error = "Errore";
            this.store.loading = false;
          })
  },
  methods: {
    handleFilter() {
      console.log(filter);
    }
  }
}
</script>

<template>
  <h3 v-if="store.error" class="text-danger">{{ store.error }}</h3>
  <AppHeader title ="Yu-Gi-Oh Api" />
  <SerchBar @filter="handleFilter"/>
  <AppMain />
</template>

<style lang="scss">
@use "./style/general.scss" as *;
</style>
