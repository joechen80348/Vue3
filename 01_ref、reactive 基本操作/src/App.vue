<template>
  <h3>Num : {{ num }}</h3>
  <button @click="add">click</button>
  <hr>
  <h3>Name : {{ person.name }}</h3>
  <h3>Hobby : {{ person.hobby }}</h3>
  <button @click="changeInfo">修改Name及Hobby</button>
</template>

<script>
  import { ref, reactive } from "vue";
  export default {
    name: "App",
    setup() {
      const num = ref(0);

      const add = () => {
        num.value++;
      };

      const person = reactive({
        name: "Mike",
        hobby: ["打電動", "睡覺"],
      });

      const changeInfo = () => {
        person.name = "Joe";
        person.hobby[1] = "追劇";
      };

      return { num, add, person, changeInfo };
    },
  };
</script>
