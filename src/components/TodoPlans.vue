<template>
  <span class="plans">{{ plans }}</span>
</template>

<script>
export default {
  props: ["plans"]
};
</script>

<style scoped>
.plans {
  display: inline-block;
  width: 90%;
  background-color: aliceblue;
  margin: auto;
}
</style>