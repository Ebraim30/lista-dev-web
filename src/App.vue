<script setup>
import { ref, computed, reactive } from 'vue'

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

const organizacao = computed(() => {
  return cidades.value.sort()
})
</script>

<template>
  <ul>
    <li v-for="(cidade, key) in organizacao" :key="key">
      {{ cidade }} -- <button @click="out(key)">Delete</button>
    </li>
  </ul>
  <div>
  <input v-model="newcity" placeholder="Digite a sua cidade" maxlength="20" size="20" />
  <button @click="add()">Adicionar</button>
  </div>
  </template>

<style scoped>


</style>

