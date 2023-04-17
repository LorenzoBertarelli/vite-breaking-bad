<script>
export default {
    name: "linksCard",
    props: {
        links: Object
    }

}
</script>

<template>
    <div class="text-center">
        <img class="card-img-top" :src="links.card_image" alt="Card image cap">
        <div class="card-body">
            <h5 class="card-title">{{ links.name }}</h5>
            <p class="card-text">{{ links.type }}</p>
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

