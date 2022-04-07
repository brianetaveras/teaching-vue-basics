<template>
  <div v-if="isOpen" class="popup-modal">
    <div @click="closeModal" class="modal-backdrop"></div>
    <div class="modal-content"><slot /></div>
  </div>
</template>

<script>
export default {
  //   props: ["isOpen", "closeModal"],
  props: {
    isOpen: {
      type: Boolean,
      required: true,
    },
    closeModal: {
      type: Function,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.popup-modal {
  .modal-backdrop {
    position: absolute;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
    background: rgba(0, 0, 0, 0.7);
    z-index: 1;
    transition: 0.5s;
  }

  .modal-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 2;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.2);
  }
}
</style>