<!-- Script -->
<script>
  // import *********
  import AppHeader from './components/AppHeader.vue'
  import AppMain from './components/AppMain.vue'
  import AppFooter from './components/AppFooter.vue'

  // export *********
  export default  {
    name: 'App',
    components: {
      AppHeader,
      AppMain,
      AppFooter,
    },

    data() {
      return {
        // 
      }
    },

    methods: {
      // 
    },

    mounted() {
      // 
    },

  }

</script>

<!-- template -->
<template>
  <header>
    <AppHeader />
  </header>

  <main>  
    <AppMain />
  </main>
  
  <footer>
    <AppFooter />
  </footer>

</template>

<!-- style -->
<style lang="scss" scoped>

@use './styles/partials/_variables' as *;

header {
  background-color: $color-primary;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
}

main {
  background-color: $color-primary;
  margin-top: 135px;
}

footer {
  background-color: $color-secondary;
}

</style>
