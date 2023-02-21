<template>
  <div class="header">
    <h1>My Todo List</h1>
    <form id="add-form">
      <input
        type="text"
        placeholder="Add new task"
      />
      <button type="submit"><i class="fas fa-plus"></i></button>
    </form>
  </div>
</template>

<script>
  import { reactive, toRef, toRefs } from "vue";

  export default {
    name: "MyHeader",
    setup() {
      return {};
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
