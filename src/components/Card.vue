<template>
    <div class="main">
        <div class="img-class">
            <img class="image-self" v-bind:src="data.image" v-bind:alt="data.title" />
        </div>
        <h4 class="title">{{ data.title }}</h4>
        <div class="body">
            <text>{{ data.description }}</text>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        data: Object
    }
}
</script>

<style scoped>
.main {
    border: 0.25px solid gray;
    border-radius: 10px;
    width: 15%;
    min-height: 250px;
    margin: 10px;
    display: flex;
    flex-direction: column;
    padding: 20px;
    box-shadow: 5px 10px 8px gray;
}
.title {
    margin-top: 170px;
    height: 50px;
    width: 100%;
    overflow-y: scroll;
    color: rgb(117, 117, 243);
}

.body {
    height: 150px;
    width: 100%;
    overflow-y: scroll;
    scrollbar-width: thin;
    scrollbar-color: black;
    color: gray;
}

.img-class {
    margin: 5px;
    align-self: center;
    height: 50px;
}

.image-self {
    height: 150px;
    width: 100%;
}
</style>