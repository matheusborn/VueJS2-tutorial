<template>
  <header>
    <h1 @click="changeTitle">{{ title }}</h1>
  </header>
</template>

<script>
import { bus } from "../main";

export default {
  props: {
    title: {
      type: String
    }
  },
  data() {
    return {
      title2: "Vue Ninjas"
    };
  },
  methods: {
    changeTitle() {
      // this.$emit("changeTitle", "Vue Wizards");
      bus.$emit("titleChanged", "Vue Wizards");
      this.title = "Vue Wizards";
    }
  }
};
</script>

<style scoped>
header {
  background: lightgreen;
  padding: 10px;
}

h1 {
  color: #222;
  text-align: center;
}
</style>
