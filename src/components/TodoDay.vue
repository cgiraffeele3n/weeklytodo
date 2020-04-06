<template>
  <div @click.self="showModal()">
    <span class="mark">{{ day }}</span>
    <span class="yobi">{{ yobi }}</span>

    <p>{{ plans }}</p>
    <modal
      v-if="show"
      @closemodal="closeModal"
      @submitplans="submitPlans"
      v-bind:day="day"
      v-bind:yobi="yobi"
    />
  </div>
</template>

<script>
import modal from "./modal.vue";
export default {
  components: {
    modal
  },
  data() {
    return {
      show: false,
      plans: ""
    };
  },
  methods: {
    showModal() {
      this.show = true;
    },
    closeModal() {
      this.show = false;
    },
    submitPlans(plans) {
      this.plans = plans;
    }
  },
  props: ["day", "yobi"]
};
</script>


<style>
.day {
  display: inline-block;
  vertical-align: middle;
  line-height: normal;
}

.yobi {
  display: inline-block;
  vertical-align: middle;
  line-height: normal;
}
</style>