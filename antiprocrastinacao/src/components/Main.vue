<script setup>
import { ref } from 'vue'

const resultado = ref("")
const resultadoGeral = ref("")
const numeroSorteio = ref(0)
const listaGeral = ref([
  "Nada",
  "Tocar Guitarra", 
  "Assistir Our Flag Means Death",
  "Assistir Doctor Who",
  "Assistir The Expanse",
  "Jogar No Man's Sky",
  "Jogar Grounded",
  "Ler Duna",
  "Ler A Torre Negra"
])
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

const gerarGeral = () => {
  numeroSorteio.value = Math.floor(Math.random()*8)+1
  resultadoGeral.value = listaGeral.value[numeroSorteio.value]
}

defineProps({
  msg: String
})
</script>

<template>
  <div>
    <h3>Games no ônibus:</h3>
    <p>{{resultado}}</p>
    <button @click="gerar()">Sortear</button>
  </div>
  <div>
    <h3>Anti Procrastinação:</h3>
    <p>{{resultadoGeral}}</p>
    <button @click="gerarGeral()">Sortear</button>
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
