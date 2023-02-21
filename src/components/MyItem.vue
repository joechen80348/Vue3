<template>
  <li class="todo-item">
    <div class="check-box">
      <div class="checkmark"></div>
    </div>
    <p class="text">Buy groceries</p>
    <div class="buttons"><button class="edit"><i class="fas fa-edit"></i></button><button class="delete"><i class="fas fa-trash"></i></button></div>
  </li>
</template>

<script>
  import { reactive, toRef, toRefs } from "vue";

  export default {
    name: "MyItem",
    setup() {
      return {};
    },
  };
</script>

<style scoped>
  .todo-item {
    display: flex;
    align-items: center;
    padding: 10px;
    margin-bottom: 10px;
    background-color: #f1f1f1;
    border-radius: 5px;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
  }
  .todo-item .text {
    font-size: 20px;
    color: #333;
    margin: 0;
    flex: 1;
  }
  .todo-item .buttons {
    display: flex;
    align-items: center;
  }
  .todo-item .buttons button {
    padding: 10px;
    margin-left: 5px;
    background-color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  .todo-item .buttons .edit {
    color: #2ecc71;
  }
  .todo-item .buttons .delete {
    color: #e74c3c;
  }
  .todo-item.completed .text {
    text-decoration: line-through;
    color: #999;
  }
  .todo-item .check-box {
    display: flex;
    align-items: center;
    margin-right: 10px;
  }
  .todo-item .check-box input[type="checkbox"] {
    width: 25px;
    height: 25px;
    margin: 0;
    cursor: pointer;
  }
  .todo-item .check-box .checkmark {
    width: 25px;
    height: 25px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-right: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }
  .todo-item .check-box .checkmark i {
    font-size: 20px;
    color: #fff;
  }

  /* Add styles for the completed checkbox */
  .todo-item .check-box .checkmark.checked {
    background-color: #2ecc71;
    border-color: #2ecc71;
  }
  .todo-item .check-box .checkmark.checked i {
    display: block;
  }
  /* Add styles for the edit form */
  .edit-form {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }
  .edit-form input[type="text"] {
    padding: 10px;
    border: none;
    border-radius: 5px;
    flex: 1;
    margin-right: 10px;
  }
  .edit-form button {
    padding: 10px 20px;
    background-color: #2ecc71;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
</style>

