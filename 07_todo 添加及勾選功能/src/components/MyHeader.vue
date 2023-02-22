<template>
  <div class="header">
    <h1>My Todo List</h1>
    <input
      type="text"
      placeholder="Add new task"
      v-model="title"
      @keyup.enter="add"
    />
  </div>
</template>

<script>
  import { nanoid } from "nanoid";
  import { ref } from "vue";

  export default {
    name: "MyHeader",
    props: {
      addTodo: {
        type: Function,
        required: true,
      },
    },
    setup(props) {
      const title = ref("");

      function add(e) {
        const text = title.value;
        if (!text.trim()) return;
        const todoObj = { id: nanoid(), title: e.target.value, done: false };
        props.addTodo(todoObj);
        title.value = "";
      }
      return { add, title };
    },
  };
</script>

<style scoped>
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;
  }
  .header form {
    display: flex;
  }
  .header h1 {
    font-size: 36px;
    color: #333;
    margin: 0;
  }
  .header input[type="text"] {
    padding: 10px;
    border: none;
    border-radius: 5px;
    width: 70%;
    margin-right: 10px;
  }
  .header button {
    padding: 10px 20px;
    background-color: #2ecc71;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
</style>
