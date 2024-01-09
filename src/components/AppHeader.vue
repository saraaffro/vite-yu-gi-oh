<script >
export default {
    name: 'AppHeader'
}

</script>

<template>
    <header>
        <a href="#" class="img-container">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg/640px-Yu-Gi-Oh%21_%28Logo%29.jpg"
                alt="logo">
        </a>
        <h1>Yu-Gi-Oh Api</h1>
    </header>
</template>

<style lang="scss" scoped>
header {
    width: 100%;
    height: 70px;
    position: fixed;
    left: 0;
    top: 0;
    z-index: 100;
    padding: 0 20px;
    background-color: white;
    display: flex;
    align-items: center;

    .img-container {
        width: 100px;
        margin-right: 20px;

        img {
            width: 100%;
        }
    }
}
</style>
