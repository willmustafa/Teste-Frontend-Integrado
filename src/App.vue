<script setup>
import MainNavbar from "./components/layout/MainNavbar.vue";
</script>

<template>
  <div>
    <MainNavbar />
    <transition>
      <router-view />
    </transition>
  </div>
</template>

<style scoped></style>
