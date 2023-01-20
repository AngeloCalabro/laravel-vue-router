<template>
  <AppHeader></AppHeader>
  <main class="container">
    <router-view></router-view>
  </main>
  <AppFooter></AppFooter>
    
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';
export default {
  name: 'App',
  components: {
    AppHeader, AppFooter
  },
  data() {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>

</style>