<template>
  <div id="weekly">
    <TodoDay
      v-for="(value, key) in weekly"
      :key="key"
      class="week"
      v-bind:day="value.day"
      v-bind:yobi="value.yobi"
    />
  </div>
</template>

<script>
import TodoDay from "./TodoDay.vue";
export default {
  components: {
    TodoDay
  },
  data() {
    return {
      weekly: []
    };
  },
  created() {
    var date = new Date();
    var week = ["日", "月", "火", "水", "木", "金", "土"];
    //今週
    var thisWeek = [];

    //週初めの日付をセット
    date.setDate(date.getDate() - date.getDay());
    week.forEach(function(value, index) {
      var day = {};
      day.yobi = value;
      date.setDate(date.getDate() + index);
      day.day = date.getDate().toString();
      thisWeek.push(day);
      date.setDate(date.getDate() - index);
    });

    this.weekly = thisWeek;
  },
  methods: {}
};
</script>

<style>
#weekly {
  display: flex;
}
.week {
  width: calc(100% / 7);
  height: 500px;
  background-color: #eeeeee;
  border: 1px solid #000000;
  position: relative;
}
</style>