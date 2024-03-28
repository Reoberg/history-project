<script setup>

import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

</script>

<template>
  <div id="app" class="d-flex flex-column">
    <Header></Header>
       <div id="app" class="flex-grow-1">
           <router-view></router-view>
       </div>
     <Footer></Footer>
  </div>
</template>

<style scoped>
.d-flex {
  display: flex;
  flex-direction: column; /* Stack children vertically */
  min-height: 100vh; /* Take at least full viewport height */
}

.flex-grow-1 {
  flex-grow: 1; /* Allow this element to grow and fill available space */
}
</style>
