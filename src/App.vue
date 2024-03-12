<script setup>
import { ref } from 'vue'

const cidades = ref([
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

const newcity = ref('')

function out(key) {
  cidades.value.splice(key, 1)
}

function add() {
  cidades.value.push(newcity.value)
  newcity.value = ''
}
</script>

<template>
  <ul>
    <li v-for="(cidade, key) in cidades" :key="key">
      {{ cidade }} -- <button @click="out(key)">Delete</button>
    </li>
  </ul>
  <input v-model="newcity" placeholder="Digite a sua cidade" maxlength="20" size="20" />
  <button @click="add()">Adicionar</button>
</template>
