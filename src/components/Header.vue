<template>
    <div class="header">
        <a class="navbar-brand" href="#">
            <img src="../assets/logo copia.png" alt="" width="45" height="">
        </a>
        <span>Select Type of Music</span>
        <select 
            class="select"
            aria-label="Default select example"
            v-model="searchGenre"
            @change="$emit('performSearch', searchGenre)"
        >
            <option value="All Music">All Music</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="Rock">Rock</option>
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

    span {
        background-color: #2e3a46;
        font-size: 18px;
        text-transform: uppercase;
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