<script>
import { store } from '../store';
import LinksCard from './LinksCard.vue';

export default{
    name: "AppMain",
    components: {
        LinksCard
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <select>
        <option value="Alien">Alien</option>
        <option value="Human">Human</option>
        <option value="Zombie">Zombie</option>
    </select>
    <div class="container">
        <h3>Found 20 cards</h3>
        <div class="row row-cols-5">
            <div class="col" v-for="links in store.links" :key="links.id">
                <LinksCard :links="links"/>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">

    select {
        font-size: 1.1rem;
        max-width: 1300px;
        margin-left: 80px; 
        padding: 10px;
        margin-top: 100px;
        background-color: white;
        border-radius: 10px;
        border: none;

        option {
            background-color: white;
            border-radius: 10px;
        }
    } 
    .container {
        background-color: white;
        max-width: 1300px;
        margin: 40px 60px; 
        display: flex;
        flex-wrap: wrap;

    h3 {
        color: white;
        background-color: rgb(29, 29, 29);
        text-align: center;
        align-items: center;
        display: flex;
        max-width: 1200px;
        width: 100%;
        height: 50px;
        padding: 10px;
        margin: 50px 60px 0 60px;
    }}

    .row {
        background-color: white;
        margin: 0px 50px ;
    }

    .col {
        width: calc((100% / 5) - 20px);
        margin: 0px 10px 10px 10px;
    }
</style>