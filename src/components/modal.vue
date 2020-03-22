<template>
  <transition name="modal" appear>
    <div class="overlay" v-on:click.self="toggleModal">
      <div class="modalWindow">
        <input v-model="plans" class="form plans" />
        <input type="submit" value="送信" v-on:click.self="toggleModal" />
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
.modal-leave {
  opacity: 0;
}

.modal-enter-to,
.modal-leave-to {
  opacity: 1;
}
.modal-enter-active > .modalWindow,
.modal-leave-active > .modalWindow {
  transition: transform 0.5s;
}

.modal-enter > .modalWindow {
  transform: translateY(-20px);
}

.modal-leave > .modalWindow {
  transform: translateY(-20px);
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