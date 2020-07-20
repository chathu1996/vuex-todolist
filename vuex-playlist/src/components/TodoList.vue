<template>
  <div>
     <todo v-for="todo in todos" v-bind:key="todo.id" v-bind:todo="todo"/>
  </div>
</template>

<script>
import Todo from './Todo'
export default {
    components: {
        Todo
    },
    computed: {
        todos(){
            return this.$store.state.todos;
        }
    }

}
</script>

<style>

</style>