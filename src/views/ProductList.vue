<template>
    <Cards :data="card_data" />
</template>

<script>
import Cards from "../components/Cards.vue"
import axios from 'axios';

export default {
    name: 'ProductList',
    components: {
        Cards
    },
    data() {
        return {
            card_data: [],
        }
    },
    async created() {
        console.log("list called")
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
</style>