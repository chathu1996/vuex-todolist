<template>
  <div class="todo-list-item">
    <div class="title">
      <span v-bind:class="{completed: todo.completed}" v-on:click="toggleTodoStatus">{{ todo.title }}</span>
    </div>
      <button v-on:click="deleteTodo">Dlete</button>
  </div>
</template>

<script>
export default {
    props: ["todo"],

    methods: {
      deleteTodo(){
        this.$store.dispatch('deleteTodo', this.todo);
      },
      toggleTodoStatus(){
        this.$store.dispatch('toggleTodoStatus', this.todo);
      }
    }
}
</script>

<style scoped>
.todo-list-item{
  width: 250px;
  margin: 5px auto;
}
.title{
  display: flex;
  justify-content: space-between;
}
.completed{
  text-decoration: line-through;
}
</style>

