<template>
  <AppHeader></AppHeader>
  <main class="container">
    <!-- <h1>{{ title }}</h1> -->
    <router-view></router-view>
  </main>
    
</template>

<script>
import AppHeader from './components/AppHeader.vue';
export default {
  name: 'App',
  components: {
    AppHeader
  },
  data() {
    return {
      title: 'Hi Vue!',
    }
  }
}
</script>

<style lang="scss" scoped>

</style>