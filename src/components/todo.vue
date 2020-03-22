<template>
  <div id="weekly">
    <div v-for="(value, key) in weekly" :key="key" class="day">
      <span class="mark">{{ value.day}}</span>
      <span class="yobi">{{ value.yobi }}</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      weekly: []
    };
  },
  created: function() {
    var date = new Date();
    var week = [
      "日曜日",
      "月曜日",
      "火曜日",
      "水曜日",
      "木曜日",
      "金曜日",
      "土曜日"
    ];
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
  }
};
</script>

<style>
#weekly {
  display: flex;
}
.day {
  width: calc(100% / 7);
  height: 300px;
  background-color: #cccccc;
  border: 1px solid #000000;
  position: relative;
}

.day:first-child {
  background-color: #dd0000;
}

.day:last-child {
  background-color: #00ccff;
}

.mark {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background-color: #aaaaaa;
  display: inline-block;
  text-align: center;
  line-height: 30px;
  position: absolute;
  margin: auto;
  left: 10px;
  top: 10px;
}

.yobi {
  display: inline-block;
  position: absolute;
  left: 50px;
  top: 10px;
}
</style>