<template>
  <form v-on:submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">Add to list</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: ""
    };
  },
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        let newTodo = {
          id: Date.now(),
          title: this.title,
          completed: false
        };
        this.$emit("add-todo", newTodo);
        this.title = "";
      }
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
  justify-content: center;
  margin: 30px 0;
}
input {
  margin-right: 20px;
  padding: 5px;
  border: 1px solid #ddeeff;
  border-radius: 5px;
  width: 250px;
}
button {
  background: #295956;
  border: none;
  color: #fff;
  border: 1px solid #fff;
  padding: 0 19px;
  text-transform: uppercase;
  border-radius: 5px;
  cursor: pointer;
}
</style>


