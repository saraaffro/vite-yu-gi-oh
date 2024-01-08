<script >
export default {
    name: 'SingleItem',
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card">
        <div class="img-container">
            <img :src="info.card_images[0].image_url" :alt="info.name">
        </div>
        <div class="card-title">{{ info.name }}</div>
        <div class="card-type">{{ info.archetype }}</div>
    </div>
</template>

<style lang="scss" scoped>
.img-container {
    width: 100%;

    img {
        width: 100%;
    }
}
</style>