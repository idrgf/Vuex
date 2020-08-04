<template>
    <div>
        <h3>Todos</h3>
        <div class="legend">
            <span>Double click pour valider</span>
            <span class="imcomplete-box"></span> = En attente
            <span class="complete-box"></span> = Effectué
        </div>
        <div class="todos">
            <div
                @dblclick="onDblClick(todo)"
                v-for="todo in allTodos" 
                v-bind:key="todo.id"
                class="todo"
                v-bind:class="{'is-complete':todo.completed}">
                {{ todo.title }}
                <i @click="deleteTodo(todo.id)" class="fa fa-times"></i>
            </div>
        </div>
    </div>
</template>

<script>
    import { mapGetters, mapActions } from 'vuex';

    export default {
        name: 'Todos',
        methods: {
            ...mapActions(['fetchTodos', 'deleteTodo', 'updateTodo']),
            onDblClick(todo) {
                const updTodo = {
                    id: todo.id,
                    title: todo.title,
                    completed: !todo.completed
                }
                this.updateTodo(updTodo);
            }
        },
        computed: mapGetters(['allTodos']),
        created(){
            this.fetchTodos()
        }
    };
</script>

<style lang="sass" scoped>
    @import "sass/style.sass"

    
</style>