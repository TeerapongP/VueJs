<template>
  <div class="nav">
    <nuxt-link to="/home" class="brand">
      <img src="../static/images/meme/268904447_1084397152296790_641230717616496266_n.jpg">
    </nuxt-link>
    <nav>
      <nuxt-link to="/">Home</nuxt-link>&nbsp|
      <nuxt-link to="/about">About</nuxt-link>
    </nav>
  </div>
</template>
<style scoped>
  img{
    height: 5rem;

    max-width: 100%;
    border-radius: 50%;
  }
  .brand{
    padding: 0.625rem;
  }
  .nav{
    padding: 0.625rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 8rem;
    font-size: 2rem;
    background-color: lightgray;
  }
</style>
