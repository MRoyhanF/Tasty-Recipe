<script setup>
  // import HomePage from "./components/pages/HomePage.vue";
  import WebHeader from "./components/header/WebHeader.vue";
  import WebFooter from "./components/footer/WebFooter.vue";
</script>

<template>
  <div>
    <WebHeader />
    <router-view/>
    <WebFooter />
  </div>
</template>