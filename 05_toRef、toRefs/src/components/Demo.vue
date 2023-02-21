<template>
  <h2>Name is: {{ name }}</h2>
  <h2>Age is: {{ age }}</h2>
  <!-- <h2>Salary is: {{ salary }}K</h2> -->
  <h2>Salary is: {{ job.j1.salary }}K</h2>
  <button @click="name+='~'">修改姓名</button>
  <button @click="age++">增長年齡</button>
  <!-- <button @click="salary++">加薪</button> -->
  <button @click="job.j1.salary++">加薪</button>

</template>

<script>
  import { reactive, toRef, toRefs } from "vue";

  export default {
    name: "Demo",
    setup() {
      let person = reactive({
        name: "Joe",
        age: 18,
        job: {
          j1: {
            salary: 20,
          },
        },
      });

      return {
        // 1. toRef
        // name: toRef(person, "name"),
        // age: toRef(person, "age"),
        // salary: toRef(person.job.j1, "salary"),

        // 2. toRefs，只能解析第一層
        ...toRefs(person),
      };
    },
  };
</script>
