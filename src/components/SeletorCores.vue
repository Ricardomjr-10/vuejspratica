<template>
    <div>
        <h1>Seletore de Cores</h1>
        <span>Vermelho: </span>
        <input type="number" v-model.number="nVerm"> <br>
        <span>Verde: </span>
        <input type="number" v-model.number="nVerde"> <br>
        <span>Azul: </span>
        <input type="number" v-model.number="nAzul"> <br>

        <div class="cor" :style="{backgroundColor: rgbColor}">Resultado:  {{ nVerm }} {{ nVerde }} {{ nAzul }}</div>
    </div>
</template>
    <script setup>
import { computed, ref } from 'vue';

    const nVerm = ref(0)
    const nVerde = ref(0)
    const nAzul = ref(0)

    const rgbColor = computed(() => {
        return `rgb(${nVerm.value},${nVerde.value},${nAzul.value})`
    }) 
   </script>

<style scoped>



</style>