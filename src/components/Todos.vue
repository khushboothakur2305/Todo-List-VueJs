<template>
  <div class="back">
    <div class="todos" v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem
        class="list"
        v-bind:todo="todo"
        v-on:del-todo="$emit('del-todo', todo.id)"
      />
    </div>
  </div>
</template>
<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  props: ["todos"],
  components: {
    TodoItem,
  },
};
</script>
<style scoped>
.todos {
  width: 80%;
  padding-left: 20%;
}
.back {
  padding: 100px;
  background-image: linear-gradient(black, gray, white);
  height: 100%;
}
.list {
  background: black;
  color: white;
}
</style>
