<template>
  <h3>{{ msg }} {{ name }}</h3>
  <button @click="test">執行Demo組件的hello事件</button>
</template>

<script>
  import { ref, reactive } from "vue";
  export default {
    name: "App",
    props: ["msg", "name"],
    emits: ["hello"],
    setup(props, context) {
      console.log(props);
      console.log(context);

      const test = () => {
        context.emit("hello", 666);
      };
      return { test };
    },
  };
</script>
