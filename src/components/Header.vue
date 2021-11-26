<template>
    <div class="header">
        <a class="navbar-brand" href="#">
            <img src="../assets/logo copia.png" alt="" width="45" height="">
        </a>
        <select 
            class="select" 
            aria-label="Default select example"
            v-model="searchGenre"
            @change="$emit('performSearch', searchGenre)"
        >
            <option value="1">All Music</option>
            <option value="2">Pop</option>
            <option value="3">Jazz</option>
            <option value="4">Metal</option>
            <option value="5">Roch</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            searchGenre: '',
        }
    }
}
</script>

<style scoped lang="scss">
.header {
    background-color: #2e3a46;
    padding: 20px;

    a {
        border-radius: 50%;
    }

    img {
       border-radius: 50%; 
    }

    .select {
        background-color: lightgray;
        color: black;
        border: none;
        margin: 1rem;
        padding: 5px 10px;
    }
}
</style>