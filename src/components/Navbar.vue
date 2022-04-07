<script setup>
import { RouterLink } from "vue-router";
import LoginPopup from "@/components/auth/LoginPopup.vue"
</script>

<template>
  <nav class="navbar-wrapper">
    <div class="container navbar">
      <div class="logo-container">
        <h1>Mandinga Experiences</h1>
      </div>
      <div class="menu-container">
        <RouterLink class="nav-link" to="/">Home</RouterLink>
        <RouterLink class="nav-link" to="/about">About</RouterLink>
        <button @click="toggleLoginModal" class="login-button">Login</button>
        <LoginPopup :isOpen="isLoginModalOpen" :closeModal="toggleLoginModal" />
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isLoginModalOpen: false,
    };
  },
  methods: {
    toggleLoginModal() {
      this.isLoginModalOpen = !this.isLoginModalOpen;
    },
  },
};
</script>

<style lang="scss">
.navbar-wrapper {
  height: 60px;
  width: 100%;
  padding: 0 20px;

  .navbar {
    height: 100%;
    display: flex;
    justify-content: start;
    align-items: center;

    .menu-container {
      display: flex;
      align-items: center;
      gap: 20px;
      margin-left: auto;

      .nav-link {
        text-decoration: none;
        color: #363636;
        font-weight: bold;
      }

      .login-button {
        height: 40px;
        background: #363636;
        color: #f1f1f1;
        padding: 0 20px;
        border-radius: 10%;
        font-weight: bold;
      }
    }
  }
}
</style>