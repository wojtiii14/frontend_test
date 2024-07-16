<template>
  <header>
    <a href="/"><img src="../assets/logo.png" alt="HTML5 Logo" /></a>
    <span class="header-title">Zadanie rekrutacyjne</span>
  </header>
</template>

<script>
export default {
  name: 'PageHeader'
};
</script>

<style scoped>
header {
  position: fixed;
  top: 0;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #333;
  color: #fff;
  padding: 1rem 2rem;
  z-index: 1000;
}

header img {
  width: 50px;
}

.header-title {
  flex: 1;
  text-align: center;
  font-size: 1.5rem;
  margin-left: 1rem;
}

@media (max-width: 960px) {
  header {
    flex-direction: column;
    align-items: flex-start;
  }

  .header-title {
    text-align: left;
    font-size: 1.25rem;
    margin-left: 0;
  }
}
</style>
