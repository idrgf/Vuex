<template>
  <div id="app">
    <div class="container">
      <AddTodo></AddTodo>
      <FilterTodos></FilterTodos>
      <todos></todos>
      
    </div>

  </div>
</template>

<script>
import Todos from './components/Todos.vue'
import AddTodo from './components/AddTodo.vue'
import FilterTodos from './components/FilterTodos.vue'

export default {
  name: 'App',
  components: {
    Todos,
    AddTodo,
    FilterTodos
  }
}
</script>

<style lang="sass">
  @import "sass/style.sass"
  
  #app 
    font-family: Avenir, Helvetica, Arial, sans-serif
    -webkit-font-smoothing: antialiased
    -moz-osx-font-smoothing: grayscale
    text-align: center
    color: #2c3e50
    margin-top: 60px
</style>
