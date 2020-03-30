<template>
  <div @click.self="toggleModal">
    <span class="mark">{{ day}}</span>
    <span class="yobi">{{ yobi }}</span>
    <modal v-if="show" @togglemodal="toggleModal" @submitplans="submitPlans" />
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
      show: false
    };
  },
  methods: {
    toggleModal() {
      this.show = !this.show;
    },
    submitPlans(plans) {
      console.log(plans);
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