<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora aritmética</h1>
      <p>
        Calcule abaixo os seus números
      </p>
    </header>
      <div>
      <!-- Campo de input para o primeiro número -->
      <input type="number" v-model.number="num1" placeholder="Digite o primeiro número">

      <!-- Campo de input para o segundo número -->
      <input type="number" v-model.number="num2" placeholder="Digite o segundo número">

      <!-- Campo de seleção para escolher a operação aritmética -->
      <select v-model="operation">
        <option value="add">Soma (+)</option>
        <option value="subtract">Subtração (-)</option>
        <option value="multiply">Multiplicação (*)</option>
        <option value="divide">Divisão (/)</option>
      </select>

      <!-- Exibição do resultado -->
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,  // Valor inicial do primeiro número
      num2: 0,  // Valor inicial do segundo número
      operation: 'add'  // Operação inicial
    };
  },
  computed: {
    result() {
      // Converte os valores para números
      const n1 = parseFloat(this.num1);
      const n2 = parseFloat(this.num2);
      
      // Realiza a operação aritmética com base na opção selecionada
      switch (this.operation) {
        case 'add':
          return n1 + n2;
        case 'subtract':
          return n1 - n2;
        case 'multiply':
          return n1 * n2;
        case 'divide':
          return n2 !== 0 ? n1 / n2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    }
  }
}
</script>

<style>
input, select {
  margin: 10px;
}
</style>
