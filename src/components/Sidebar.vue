<script setup lang="ts">
import { shallowRef } from "vue";

const isSidebarOpen = shallowRef<Boolean>(false);
function toggleSidebar() {
  isSidebarOpen.value = !isSidebarOpen.value;
}
</script>
<template>
  <div class="sidebar">
    <aside
      :vue:is-open="isSidebarOpen"
      @mouseenter="toggleSidebar()"
      @mouseleave="toggleSidebar()"
    >
      <ul class="sidebar-head">
        <li>
          <img src="../assets/logo.png" alt="logo" width="32" height="32" />
        </li>
      </ul>
      <h4 :transparent="!isSidebarOpen">Menu</h4>
    </aside>
  </div>
</template>
    
<style scoped lang="scss">
@use "@/assets/scss/colors" as clr;
$sidebar-width: 4rem;
$toggle-duration: 300ms;
$sidebar-padding-inline-start: 1rem;
aside {
  color: clr.$primary;
  background: clr.$bg-dark;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  padding-block: 1rem;
  transition: all $toggle-duration;
  width: $sidebar-width;
}
aside[vue\:is-open="true"] {
  width: 3 * $sidebar-width;
}

li {
  min-width: fit-content;
  cursor: pointer;
  padding-inline-start: $sidebar-padding-inline-start;
  
  }
.sidebar-head {
  position: relative;
  padding-left: 0 !important;
}
h4 {
  opacity: 0.5;
  transition: opacity $toggle-duration;
}
h4[transparent="true"] {
  opacity: 0;
}

</style>