<template>
  <ul id="todo-list">
    <MyItem
      v-for="todoObj in todos"
      :key="todoObj.id"
      :todo="todoObj"
    />
  </ul>
</template>

<script>
  import MyItem from "./MyItem.vue";

  export default {
    name: "MyList",
    components: { MyItem },
    props: ["todos"],
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

