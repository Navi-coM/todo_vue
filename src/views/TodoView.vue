<template>
  <div class="home">
    <img src="../assets/logo.png" class="main_logo" alt="Vue Logo" />
    <h1>Application Todo Beetroot</h1>
    <AddTodo v-on:add-todo="addTodo" />
    <Loader v-if="loading" />
    <TodoList v-bind:todos="todos" v-on:remove-todo="removeTodo" />
  </div>
</template>
    
<script>
import TodoList from "@/components/todo/TodoList";
import AddTodo from "@/components/todo/AddTodo";
import Loader from "@/components/todo/Loader";

export default {
  name: "TodoView",
  data() {
    return {
      todos: [
        // { id: 1, title: "Learning JS", completed: false },
        // { id: 2, title: "Learning VueJS", completed: false },
        // { id: 3, title: "Learning React", completed: false },
        // { id: 4, title: "Learning PHP", completed: false },
        // { id: 5, title: "Learning Angular", completed: false }
      ],
      loading: true
    };
  },
  mounted() {
    fetch("./todos.json")
      .then(response => response.json())
      .then(json => {
        setTimeout(() => {
          this.todos = json;
          this.loading = false;
        }, 2500);
      });
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo);
    }
  },
  components: {
    TodoList,
    AddTodo,
    Loader
  }
};
</script>

<style scoped>
.main_logo {
  width: 75px;
}

a {
  text-decoration: none;
  color: #314145;
  font-size: 22px;
}
img {
  width: 60px;
  height: auto;
}
h1 {
  font-size: 24px;
  padding-bottom: 10px;
  color: #d6e2e5;
  border-bottom: 1px solid #2b413e;
}
</style>