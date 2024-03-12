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

function out (key) {
  cidades.value.splice(key, 1)
}



function
</script>

<template>
  <ul>
    <li v-for="(cidade, key) in organizado" :key="key">
      {{ cidade }} -- <button @click="out(key)">Delete</button>
    </li>
  </ul>
</template>
