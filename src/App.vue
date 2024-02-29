<template>
  <main>
    <div class="container">
      <h1>歡迎使用 re.works 待辦事項！</h1>
      <todo-add :tid = "todos.length" @add-todo="addTodo" />
      <todo-filter />
      <todo-list :todos = "todos" />
    </div>
  </main>
</template>

<script>
import { ref } from "vue";

import TodoAddVue from './components/TodoAdd.vue';
import TodoFilter from './components/TodoFilter.vue';
import TodoFilterVue from './components/TodoFilter.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: "App",
  components: { TodoAdd, TodoFilter, TodoListTodoListTodoFilter },
  setup() {
    const todos = ref([]);
    const addTodo = (todo) => todos.value.push(todo);
    return {
      todos,
      addTodo,
    };
  },
  /*  */
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Helvetica, "Microsoft JhengHei";
}

/* 整個頁面 */
main {
  width: 100vw;
  min-height: 100vh;
  display: grid;
  align-items: center;
  justify-items: center;
  background: rgb(203, 210, 240);
}

.container {
  width: 60%;
  min-width: 400px;
  box-shadow: 0px 0px 24px rgb(0, 0, 0, 0.15);
  border-radius: 24px;
  padding: 48px 28px;
  background-color: rgb(245, 246, 252);
}

h1 {
  margin: 24px 0;
  font-size: 28px;
  color: #414873;
}








</style>
