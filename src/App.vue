<template>
  <div id="app">
    <h1>Vue 3 Calculator</h1>
    <div>
      <input v-model.number="number1" type="number" placeholder="Number 1" @input="calculate" />
      <input v-model.number="number2" type="number" placeholder="Number 2" @input="calculate" />
    </div>
    <div>
      <select v-model="operation" @change="calculate">
        <option value="add">Add (+)</option>
        <option value="subtract">Subtract (-)</option>
        <option value="multiply">Multiply (×)</option>
        <option value="divide">Divide (÷)</option>
      </select>
    </div>
    <h2>Result: {{ result }}</h2>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add',
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case 'add':
          this.result = this.number1 + this.number2;
          break;
        case 'subtract':
          this.result = this.number1 - this.number2;
          break;
        case 'multiply':
          this.result = this.number1 * this.number2;
          break;
        case 'divide':
          this.result = this.number2 ? this.number1 / this.number2 : 'undefined'; // Avoid division by zero
          break;
      }
    },
  }
}
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}
input, select {
  margin: 20px;
  padding: 10px;
  font-size: 16px;
}
h1, h2 {
  color: #2c3e50;
}
</style>
