<script setup>
import PopupModal from "@/components/PopupModal.vue";
</script>
<template>
  <PopupModal :isOpen="isOpen" :closeModal="closeModal">
    <form @submit.prevent="handleLoginSubmit" class="login-popup">
      <h2 class="login-popup-title">Login</h2>
      <input
        v-model="email"
        class="login-popup-input"
        placeholder="Email"
        type="email"
      />
      <input
        v-model="password"
        class="login-popup-input"
        placeholder="****"
        type="password"
      />
      <button type="submit" class="login-popup-button">Login</button>
      <div v-if="error.length" class="error">{{ error }}</div>
    </form>
  </PopupModal>
</template>

<script>
export default {
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
  data() {
    return {
      email: "",
      password: "",
      accounts: {
        "frederick@yo.com": "papirucho",
        "brian@yo.com": "papirucha",
      },
      error: "",
    };
  },

  methods: {
    handleLoginSubmit() {
      if (this.accounts[this.email] === this.password) {
        this.closeModal();
        this.error = "";
        alert("Bienvenido!");
        return;
      }

      this.error = "La macaste mi hermano :(";
    },
  },
};
</script>

<style lang="scss">
.login-popup {
  background: #f1f1f1;
  padding: 20px;

  .login-popup-title {
    text-align: center;
    margin-bottom: 20px;
  }

  .login-popup-input,
  .login-popup-button {
    height: 40px;
    width: 300px;
    display: block;
    margin: 10px 0;
  }
  .login-popup-input {
    padding: 10px;
  }
}
</style>