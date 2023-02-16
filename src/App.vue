<script setup>
import { reactive } from 'vue';

const estado = reactive({
  operacao: '',
  n1: '',
  n2: '',
}
)

const calcular = () => {
  const operacao = estado.operacao;
  const n1 = parseInt(estado.n1);
  const n2 = parseInt(estado.n2);

  switch (operacao) {
    case 'Somar':
    return n1 + n2;
      break;
    case 'Subtrair':
      return n1 - n2
      break;
    case 'Dividir':
    return n1 / n2;
      break;
    case 'Multiplicar':
    return n1 * n2
      break;
    default: 'Erro'
  }
}
calcular();


</script>

<template>
  <div class="container">
    <form class="col-4 mt-4 mb-4">
      <label for="Número 1">Primeiro Numero</label>
      <input @keyup="evento => estado.n1 = evento.target.value" class="form-control" type="number">
      <label for="Número 1">Segundo Numero</label>
      <input @keyup="evento => estado.n2 = evento.target.value" class="form-control" type="number">
    </form>
    <select @change="evento => estado.operacao = evento.target.value" name="" id="">
      <option disable value="">Escolha uma Operação</option>
      <option value="Somar">Somar</option>
      <option value="Subtrair">Subtrair</option>
      <option value="Dividir">Dividir</option>
      <option value="Multiplicar">Multiplicar</option>
    </select>
    <div class="div">
      O Resultado é {{ calcular() }}
    </div>
  </div>
</template>

<style scoped>

</style>
