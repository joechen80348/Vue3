<template>
  <ul id="todo-list">
    <MyItem />
  </ul>
</template>

<script>
  import { reactive, toRef, toRefs } from "vue";
  import MyItem from "./MyItem.vue";

  export default {
    name: "MyList",
    components: { MyItem },
    setup() {
      return {};
    },
  };
</script>

