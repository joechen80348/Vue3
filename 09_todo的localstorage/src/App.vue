<template>
  <div class="container">
    <MyHeader :addTodo="addTodo" />
    <MyList
      :todos="todos"
      :deleteTodo="deleteTodo"
    />
  </div>
</template>

<script>
  import { reactive, ref, watch, onMounted } from "vue";

  import MyHeader from "./components/MyHeader.vue";
  import MyList from "./components/MyList.vue";

  export default {
    name: "App",
    components: { MyHeader, MyList },
    setup() {
      const todos = reactive([]);

      // onMounted
      onMounted(() => {
        if (JSON.parse(localStorage.getItem("todo_key")) === null) return;

        const data = JSON.parse(localStorage.getItem("todo_key"));
        data.forEach((todoObj) => {
          todos.push(todoObj);
        });
      });

      // watch
      const todoWatch = watch(
        todos,
        (value) => {
          localStorage.setItem("todo_key", JSON.stringify(value));
        },
        { deep: true }
      );

      function addTodo(todoObj) {
        todos.unshift(todoObj);
      }

      function deleteTodo(index) {
        todos.splice(index, 1);
      }

      return { todos, addTodo, deleteTodo, todoWatch };
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
