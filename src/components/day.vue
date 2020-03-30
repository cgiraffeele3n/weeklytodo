<template>
  <div>
    <span class="mark">{{ day}}</span>
    <span class="yobi">{{ yobi }}</span>
  </div>
</template>

<script>
export default {
  props: ["day", "yobi"]
};
</script>


<style>
.day {
  display: inline-block;
  text-align: center;
}

.yobi {
  display: inline-block;
  text-align: center;
}
</style>