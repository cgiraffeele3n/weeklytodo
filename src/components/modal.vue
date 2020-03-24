<template>
  <transition name="modal" appear>
    <div class="overlay" v-on:click.self="toggleModal">
      <div class="modalWindow">
        <ol id="forms">
          <li>
            <input v-model="plans" class="form plans" />
          </li>
          <li>
            <input type="button" value="送信" v-on:click.self="submitPlans" />
          </li>
        </ol>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      plans: ""
    };
  },
  methods: {
    toggleModal: function() {
      this.$emit("togglemodal");
    },
    submitPlans: function() {
      this.$emit("submitplans", this.plans);
      this.$emit("togglemodal");
    }
  }
};
</script>

<style>
.modalWindow {
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fff;
  width: 40%;
  height: 30%;
  border-radius: 4px;
  z-index: 1;
}

.overlay {
  display: flex;
  align-items: center;
  justify-content: center;
  position: fixed;
  z-index: 2;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}

.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.5s;
}

.modal-enter,
.modal-leave-to {
  opacity: 0;
}

.modal-enter-to,
.modal-leave {
  opacity: 1;
}

#forms {
  list-style: none;
}

.form {
  border: none;
  outline: none;
  border-bottom: 2px solid #1b2538;
  background: transparent;
}

.form :focus {
  border-bottom: 2px solid #da3c41;
  background: transparent;
  outline: none;
}
</style>