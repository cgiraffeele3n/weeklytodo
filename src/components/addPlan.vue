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
    toggleModal: function() {
      this.show = !this.show;
    },
    submitPlans: function(plans) {
      console.log(plans);
    }
  }
};
</script>

<style>
.addButton {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: inline-block;
  line-height: 50px;
  text-align: center;
  background-color: #cccccc;
  position: absolute;
  margin: auto;
  right: 10px;
  bottom: 10px;
}
</style>