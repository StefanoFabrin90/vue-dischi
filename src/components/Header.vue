<template>
    <div class="header">
        <a class="navbar-brand" href="#">
            <img src="../assets/logo copia.png" alt="" width="45" height="">
        </a>
    </div>
</template>

<script>
export default {
    name: 'Header',
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
}
</style>