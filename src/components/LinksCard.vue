<script>
export default {
    name: "linksCard",
    props: {
        linksObj: Object
    }

}
</script>

<template>
    <div class="card">
        <img class="card-img-top" :src="linksObj.card_images[0].image_url" alt="Card image cap">
        <div class="card-body">
            <h5 class="card-title">{{ linksObj.name }}</h5>
            <p class="card-text">{{ linksObj.archetype }}</p>
        </div>
    </div>
</template>

<style>
    .text-center {
        background-color: white;
    }

    h5 {
        color: white;
    }
</style>

