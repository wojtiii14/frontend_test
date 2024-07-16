<template>
  <footer>
    <div class="footer-content">
      <div class="css-awesome" @mouseenter="animateCSS" @mouseleave="resetCSS">
        CSS IS AWESOME
      </div>
      <button @click="showOptions">POKAŻ</button>
      <div v-if="optionsVisible" class="options">
        <button @click="resetSettings">Zresetuj ustawienia</button>
        <button @click="addName">Pokaż dane osobowe</button>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'PageFooter',
  data() {
    return {
      optionsVisible: false
    };
  },
  methods: {
    showOptions() {
      this.optionsVisible = !this.optionsVisible;
    },
    addName() {
      const header = document.querySelector('header-title');
      if (!header.innerText.includes('Wojciech Kaczmarek')) {
        header.innerText += ' - Wojciech Kaczmarek';
      }
    }
  }
};
</script>

<style scoped>
footer {
  margin-top: auto;
  padding: 1rem 2rem;
  background-color: #333;
  color: #fff;
  text-align: center;
  position: relative;
}

.css-awesome {
  cursor: pointer;
  transition: transform 0.3s;
  display: inline-block;
}

.css-awesome:hover {
  transform: rotate(360deg);
}

.options {
  display: flex;
  justify-content: space-around;
  margin-top: 1rem;
}

.options button {
  background-color: #fff;
  border: 1px solid #333;
  color: #333;
  padding: 0.5rem 1rem;
  cursor: pointer;
}

.options button:hover {
  background-color: rgb(71, 183, 132);
}
</style>
