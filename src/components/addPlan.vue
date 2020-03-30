<template>
  <div>
    <span class="addButton" @click="toggleModal">+</span>
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
  }
};
</script>

<style>
</style>