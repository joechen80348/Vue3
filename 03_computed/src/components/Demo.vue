<template>
  姓:<input
    type="text"
    v-model="person.firstName"
  >
  名:<input
    type="text"
    v-model="person.lastName"
  >

  全名:
  <input
    type="text"
    v-model="person.fullName"
  >
</template>

<script>
  import { ref, reactive, computed } from "vue";
  export default {
    name: "App",

    setup() {
      const person = reactive({
        firstName: "Joe",
        lastName: "Chen",
      });

      // 簡寫
      // person.fullName = computed(() => {
      //   return `${person.firstName}-${person.lastName}`;
      // });

      // 完整
      person.fullName = computed({
        get() {
          return `${person.firstName}-${person.lastName}`;
        },
        set(value) {
          const fullNameArr = value.split("-");
          person.firstName = fullNameArr[0];
          person.lastName = fullNameArr[1];
        },
      });

      return { person };
    },
  };
</script>
