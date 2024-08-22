<script setup>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
</script>

<template>

  <header>
    <AppHeader/>
  </header>

  <main>
    <router-view></router-view>
  </main>

  <footer>
    <AppFooter/>
  </footer>

</template>

<style lang="scss">
@use './styles/general.scss';
</style>
