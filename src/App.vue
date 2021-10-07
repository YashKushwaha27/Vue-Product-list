<template>
  <div class="main">
    <Header />
    <Cards :data="card_data" />
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import Cards from "./components/Cards.vue"
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Cards
  },
  data() {
    return {
      card_data: []
    }
  },
  async created() {
    this.card_data = await this.fetchData()
  },
  methods: {
    async fetchData() {
      const res = await axios.get('https://fakestoreapi.com/products')
      const data_res = await res.data
      return data_res
    }
  }

}
</script>

<style scoped>
.main {
  height: 100%;
  width: 100%;
}
</style>
