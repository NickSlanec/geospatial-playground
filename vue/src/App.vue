<!-- https://dribbble.com/shots/20210947-Music-app-design-mobile-app -->
<template>
  <main>
    <Dashboard/>
  </main>
</template>

<script>
import axios from "axios";
import Dashboard from './components/Dashboard.vue';
export default {
  components: { Dashboard },
  data() {
    return {
      
    };
  },
  methods: {
    
  },
  mounted() { },
}
</script>

<style>
body {
  font-family: var(--font-family);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

</style>