<script setup>
import { ref } from 'vue'

const cidadess = ref([
  'São Paulo',
  'Rio de Janeiro',
  'Belo Horizonte',
  'Salvador',
  'Fortaleza',
  'Curitiba',
  'Manaus',
  'Recife',
  'Porto Alegre',
  'Brasília'
])

function adicionar(index) {
  cidadess.value[index].quantidade++
}

function novo(index) {
  cidadess.value[index].adicionar
}
</script>
<template>
  <ul>
    <li v-for="(cidade, index) in cidadess">
      {{ cidade.cidades }} <button @click="adicionar(index)"></button>
      <button @click="novo">adicionar</button>
    </li>
  </ul>
</template>
