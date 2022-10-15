<template>
  <li class="list__item">
    <span v-bind:class="{crossed: todo.completed}">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed" />
      <b>{{ index + 1 }}</b>
      {{ todo.title }}
    </span>
    <button class="close" v-on:click="$emit('remove-todo', todo.id)">X</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    },
    index: Number
  }
};
</script>

<style scoped>
li {
  max-width: 680px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  text-align: center;
  padding: 5px;
  color: #f8eff8;
  font-size: 17px;
  background: #598c89;
  padding: 10px;
  border: 1px solid #b8cccc;
  border-radius: 8px;
  margin-bottom: 5px;
  cursor: pointer;
}
li:hover {
  background: #4b6b69;
  transition: all 0.2s linear;
}
span {
  margin-right: 8px;
  min-width: 200px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
input,
b {
  margin-right: 10px;
}
.btn-close {
  margin: 0 10px;
  border: none;
  outline: none;
  background-color: #204647;
  border-radius: 50%;
  color: #fff;
  font-size: 16px;
  cursor: pointer;
}

.close {
  border: none;
  outline: none;
  border-radius: 50%;
  padding: 6px 10px;
  background: #476062;
  color: #fff;
  cursor: pointer;
}
.close:hover {
  background: #364546;
}
.crossed {
  text-decoration: line-through;
}
</style>


