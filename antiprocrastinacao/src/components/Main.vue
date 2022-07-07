<script setup>
import { ref } from 'vue'

const resultado = ref("")
const numeroSorteio = ref(0)
const listaGeral = ref([])
const listaGueiminho = ref([
  "Nada",
  "Golden Sun",
  "DBZ - Legendary Super Warriors",
  "Harvest Moon 3",
  "Harry Potter"
])

const gerar = () => {
  numeroSorteio.value = Math.floor(Math.random()*4)+1
  resultado.value = listaGueiminho.value[numeroSorteio.value]
}

defineProps({
  msg: String
})
</script>

<template>
  <div>
    <p>{{resultado}}</p>
    <button @click="gerar()">Sortear</button>
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
