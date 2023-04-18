<script>
import { store } from '../store';

export default{
    name: "SerchBar",
    emits: ["filter"],
    data() {
        return {
            store,
            statusOptions: ["Alien", "Ally of Justice" , "Ancient Gear"]
        }
    }
}
</script>

<template>
    <select name="archetype" id="archetype" v-model="store.selectArchetype">
        <option value="">All</option>
        <option :value="archetype" v-for="archetype in statusOptions">{{ archetype }}</option>
    </select>
    <button @click="$emit('filter')" class="btn btn-warning">Search</button> 
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

    .btn-warning {
        background-color: white;
        margin-bottom: 3px;
        margin-left: 10px;
        padding: 8px;

    }
</style>
