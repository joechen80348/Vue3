<template>

  <div class="container">
    <MyHeader />
    <MyList />
  </div>
</template>

<script>
  import MyHeader from "./components/MyHeader.vue";
  import MyList from "./components/MyList.vue";

  export default {
    name: "App",
    components: { MyHeader, MyList },
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
