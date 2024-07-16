<template>
    <div class="radio-button">
      <input type="radio" :id="id" :value="value" v-model="localModelValue" />
      <label :for="id">{{ label }}</label>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RadioButton',
    props: {
      id: String,
      value: String,
      label: String,
      modelValue: String
    },
    computed: {
    localModelValue: {
        get() {
            return this.modelValue
        },
        set(newValue) {
            this.$emit('update:modelValue', newValue)
        },
    },
},
  };
  </script>
  
  <style scoped>
  .radio-button {
    margin: 0.5rem 0;
  }
  </style>
  