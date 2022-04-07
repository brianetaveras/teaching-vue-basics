<template>
  <header class="home-header">
    <img
      class="home-header-image"
      src="https://images.unsplash.com/photo-1649083048269-8bfb755e7b87?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1471&q=80"
      alt="Site header - Fully decorated living room."
    />
    <div class="home-header-search-bar">
      <h1 class="home-header-search-bar-title">
        Book your experience in the most luxurious hood.
      </h1>
      <input
        placeholder="Find your Mandinga getaway"
        type="text"
        class="home-header-search-bar-input"
      />
    </div>
  </header>
</template>

<style lang="scss">
.home-header {
  position: relative;
  height: 600px;
  width: 100%;

  .home-header-image {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .home-header-search-bar {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;

    .home-header-search-bar-input {
      max-width: 500px;
      width: 100%;
      height: 60px;
      border-radius: 30px;
      border: none;
      box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.2);
      padding: 20px;
    }
  }
}
</style>