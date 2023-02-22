<template>
  <ul id="todo-list">
    <MyItem
      v-for="(todoObj, index) in todos"
      :key="todoObj.id"
      :todo="todoObj"
      :deleteTodo="deleteTodo"
      :index="index"
    />
  </ul>
</template>

<script>
  import MyItem from "./MyItem.vue";

  export default {
    name: "MyList",
    components: { MyItem },
    props: ["todos", "deleteTodo"],
    setup() {
      // function checkTodo(id) {
      //   this.todos.foreach((todo) => {
      //     if (todo.id === id) todo.done = !todo.done;
      //   });
      // }

      return {};
    },
  };
</script>

