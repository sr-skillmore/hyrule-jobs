<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('zelda')">change name</button>
    <button @click="changeAge(30)">change age</button>
  </div>
</template>

<script lang="ts">
// this lesson uses Options API
import { defineComponent, reactive, ref, toRefs } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    // const state = reactive({
    //   name: "Link",
    //   age: 25 as number | string,
    // });

    // // state.name = 999; // cannot change type as detected as string by inference
    // // state.age = "26"; // can be string or number
    // // state.age = 30; // can be string or number

    // return { ...toRefs(state) };

    const name = ref("Link");
    const age = ref<number | string>(25);

    return { name, age };
  },
  methods: {
    changeName(name: string) {
      this.name = name;
      return name;
    },
    changeAge(age: number | string) {
      this.age = age;
      return age;
    },
  },
});
</script>

<style></style>
