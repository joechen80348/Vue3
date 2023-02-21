<template>
  <h3>Num : {{ num }}</h3>
  <button @click="add">click</button>
  <hr>
  <h3>Name : {{ person.name }}</h3>
  <h3>Hobby : {{ person.hobby }}</h3>
  <h3 v-show="person.sex">Sex : {{ person.sex }}</h3>
  <button @click="addInfo">新增性別</button>
  <button @click="updateInfo">修改Name及Hobby</button>
  <button @click="deleteInfo">刪除性別</button>
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

      // 新增
      const addInfo = () => {
        person.sex = "男";
      };

      // 修改
      const updateInfo = () => {
        person.name = "Joe";
        person.hobby[1] = "追劇";
      };

      const deleteInfo = () => {
        delete person.sex;
      };

      return { num, add, person, addInfo, updateInfo, deleteInfo };
    },
  };
</script>
