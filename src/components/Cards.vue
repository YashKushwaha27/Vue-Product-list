<template>
    <div class="cardsArray">
        <Card v-for="d in data" :key="d" :data="d" />
    </div>
</template>

<script>
import Card from './Card.vue'
export default {
    name: 'Cards',
    components: {
        Card
    },
    props: {
        data: Array
    },
    mounted() {
        console.log("mounted Cards.", this.data)
    }
}
</script>

<style scoped>
.cardsArray {
    display: flex;
    flex-direction: row;
    border: 1px solid black;
    max-width: 100%;
    flex-wrap: wrap;
    align-content: space-between;
    padding-left: 15px;
}
</style>