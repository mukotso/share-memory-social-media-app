<template>
  <div class="landing-page">
    <div class="header">
      <h1>Welcome to Share Memories Social Media APP</h1>
    </div>
    <div class="content">
      <p>
        Sign in or register to get started!
      </p>
    </div>
    <div class="cta-buttons">
      <router-link to="/login">
        <button class="p-button p-button-primary">LOGIN</button>
      </router-link>
      <router-link to="/register">
        <button class="p-button p-button-success">REGISTER</button>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LandingPage',
};
</script>

<style scoped>
 .landing-page {
  text-align: center;
  padding: 20px;
} 
</style>

