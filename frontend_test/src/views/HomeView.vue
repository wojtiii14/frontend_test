<template>
  <main>
    <section class="block first">
      <h2>Blok pierwszy</h2>
      <RadioButton id="option1" value="option1" label="Opcja pierwsza" v-model="selectedOption" />
      <RadioButton id="option2" value="option2" label="Opcja druga" v-model="selectedOption" />
      <RadioButton id="option3" value="option3" label="Opcja losowa" v-model="selectedOption" />
    </section>
    <section class="block second">
      <h2>Blok drugi</h2>
      <button @click="replaceText">ZASTĄP</button>
      <button @click="appendText">DOKLEJ</button>
    </section>
    <section class="block third">
      <h2>Blok z długą nazwą która sama się przytnie ...</h2>
      <div v-html="content"></div>
    </section>
  </main>
</template>

<script>
import RadioButton from '@/components/RadioButton.vue';
import data from '@/data.json';

export default {
  name: 'HomeView',
  components: {
    RadioButton
  },
  data() {
    return {
      selectedOption: '',
      content: '',
      data: data
    };
  },
  methods: {
    replaceText() {
      const index = this.getSelectedIndex();
      this.content = `<p>${this.data[index].text}</p>`;
    },
    appendText() {
      const index = this.getSelectedIndex();
      if (!this.content.includes(this.data[index].text)) {
        this.content += `<p>${this.data[index].text}</p>`;
      } else {
        alert('Tekst już istnieje');
      }
    },
    getSelectedIndex() {
      if (this.selectedOption === 'option1') return 0;
      if (this.selectedOption === 'option2') return 1;
      if (this.selectedOption === 'option3') return Math.floor(Math.random() * (this.data.length - 2)) + 2;
      return 0;
    }
  }
};
</script>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 5rem 2rem 2rem;
  flex: 1;
}

.block {
  margin: 1rem 0;
  padding: 1rem;
  background-color: #fff;
  border: 1px solid #ccc;
  border-radius: 5px;
  width: 100%;
  max-width: 960px;
}

.block h2 {
  margin-top: 0;
}

.radio-button {
  margin: 0.5rem 0;
}

button {
  background-color: #333;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  margin: 0.5rem 0;
}

button:hover {
  background-color: rgb(71, 183, 132);
}
</style>
