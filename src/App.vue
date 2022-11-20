<script setup>
  import { RouterView } from 'vue-router';
</script>

<template>
  <div class="dark-theme">
    <div class="content d-flex align-items-center vh-100 justify-content-center ms-auto">
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
  @import "./assets/base.css";
  .content {
    padding: 100px 0px;
  }
</style>