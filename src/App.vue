<script>
// import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
import Accordion from './components/accordion.vue';
export default {
  components: {
    Sidebar,
    Accordion
},

}
</script>

<template>
  <div id="root">
    <Sidebar/>
    <Accordion/>
  </div>
</template>

<style scoped lang="scss">
  #root {
    display: grid;
    grid-template-areas: 'sidebar router-view';
    grid-template-columns: auto 1fr;
    font-family: sans-serif;
  }
  .sidebar {
    grid-area: 'sidebar';
  }
  .router-view {
    grid-area: 'router-view';
    padding: 1rem;
  }
  </style>
