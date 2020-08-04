<template>
    <div>
        Filter Todos
        <select v-on:change="filterTodos($event)">
            <option value="200">200</option>
            <option value="200">100</option>
            <option value="200">50</option>
            <option value="200">20</option>
            <option value="200">10</option>
            <option value="200">5</option>
        </select>
    </div>
</template>

<script>
import { mapActions } from 'vuex'
    export default {
        name:'FilterTodos',
        methods: mapActions(["filterTodos"])
    }
</script>

<style lang="scss" scoped>

</style>