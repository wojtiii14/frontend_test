<template>
  <div class="app-container">
    <Header />
    <HomeView />
    <Footer />
  </div>
</template>

<script>
import Header from './components/PageHeader.vue';
import Footer from './components/PageFooter.vue';
import HomeView from './views/HomeView.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    HomeView
  }
};
</script>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
</style>
