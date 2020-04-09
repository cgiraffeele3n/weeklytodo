<template>
  <div @click.self="showModal()">
    <span class="mid">{{ day }}</span>
    <span class="mid">{{ yobi }}</span>

    <todoplans v-bind:plans="value" v-for="(value,key) in plans" :key="key" />
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
import todoplans from "./TodoPlans.vue";
export default {
  components: {
    modal,
    todoplans
  },
  data() {
    return {
      show: false,
      plans: []
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
      this.plans.push(plans);
    }
  },
  props: ["day", "yobi"]
};
</script>


<style scoped>
.mid {
  display: inline-block;
  text-align: center;
}
</style>