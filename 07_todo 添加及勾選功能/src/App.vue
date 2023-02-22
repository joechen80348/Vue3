<template>
  <div class="container">
    <MyHeader :addTodo="addTodo" />
    <MyList :todos="todos" />
  </div>
</template>

<script>
  import { reactive, ref } from "vue";

  import MyHeader from "./components/MyHeader.vue";
  import MyList from "./components/MyList.vue";

  export default {
    name: "App",
    components: { MyHeader, MyList },
    setup() {
      const todos = reactive([
        { id: "001", title: "吃飯", done: true },
        { id: "002", title: "睡覺", done: false },
      ]);

      function addTodo(todoObj) {
        todos.unshift(todoObj);
      }

      return { todos, addTodo };
    },
  };
</script>

<style scoped>
  .container {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
  }
</style>
