<script setup>
import { ref } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('somar');

function calcularResultado() {
  switch (operacao.value) {
    case 'somar':
      return Number(numero1.value) + Number(numero2.value);
    case 'subtrair':
      return Number(numero1.value) - Number(numero2.value);
    case 'multiplicar':
      return Number(numero1.value) * Number(numero2.value);
    case 'dividir':
      return numero2.value !== 0 ? Number(numero1.value) / Number(numero2.value) : 'Não é possível dividir por zero';
    default:
      return 'Operação inválida';
  }
}
</script>

<template>
  <div id="app" class="container mt-5">
    <div class="row justify-content-center">
      <div class="col-md-6">
        <h2 class="text-center mb-4">Calculadora Vue.js</h2>

        <div class="mb-3">
          <label for="numero1" class="form-label">Número 1:</label>
          <input type="number" class="form-control" v-model.number="numero1" id="numero1" placeholder="Número 1">
        </div>

        <div class="mb-3">
          <label for="numero2" class="form-label">Número 2:</label>
          <input type="number" class="form-control" v-model.number="numero2" id="numero2" placeholder="Número 2">
        </div>

        <div class="mb-3">
          <label for="operacao" class="form-label">Operação:</label>
          <select class="form-select" v-model="operacao" id="operacao">
            <option value="somar">Somar</option>
            <option value="subtrair">Subtrair</option>
            <option value="multiplicar">Multiplicar</option>
            <option value="dividir">Dividir</option>
          </select>
        </div>

        <p class="mb-5 fs-5 fw-bold">Resultado: {{ calcularResultado() }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
