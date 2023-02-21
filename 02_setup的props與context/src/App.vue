<template>
  <Demo
    @hello="showMsg"
    msg="Hello"
    name="Joe"
  ></Demo>
</template>

<script>
  import Demo from "./components/Demo.vue";

  export default {
    name: "App",
    components: { Demo },
    setup() {
      const showMsg = (value) => {
        alert(`觸發 showMsg 參數是 : ${value}`);
      };

      return { showMsg };
    },
  };
</script>
