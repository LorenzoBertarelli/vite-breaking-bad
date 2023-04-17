<script>
export default{
    name: "AppHeader",
    props: {
        title: String
    }
}
</script>

<template>
    <h1>{{ title }}</h1> 
</template>

<style scoped lang="scss">
    h1 {
        position: absolute;
        align-items: center;
        display: flex;
        background-color: white;
        height: 60px;
        width: 100%;
        padding: 20px;
    }
</style>