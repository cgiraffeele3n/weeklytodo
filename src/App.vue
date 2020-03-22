<template>
  <div id="app">
    <div id="header"></div>
    <todo />
    <addplan />
  </div>
</template>

<script>
import todo from "./components/todo.vue";
import addplan from "./components/addPlan.vue";

export default {
  name: "App",
  components: {
    todo,
    addplan
  }
};
</script>

<style>
#header {
  width: 100%;
  height: 50px;
  margin-bottom: 10px;
  background-color: #aaffcc;
}
</style>
