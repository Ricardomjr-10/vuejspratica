<template>
    <div>
        <h1>Seletore de Cores</h1>
        <div>
            <label for="vermelho">Vermelho: </label>
            <input type="number" v-model.number="nVerm" min="0" max="255"> 
        </div>
        <div>
            <label for="verder">Verde: </label>
            <input type="number" v-model.number="nVerde" min="0" max="255"> 
        </div>
        <div>
            <label for="azul">Azul: </label>
            <input type="number" v-model.number="nAzul" min="0" max="255"> 
        </div>

        <div class="cor" :style="{backgroundColor: rgbColor}"></div>
        <p style="margin-top: 10px;">Codigo Hexadecimal: {{ hexColor }}</p>
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

    const hexColor = computed(() => {
        const toHex = (c) => {
            const hex = c.toString(16)
            return hex.length === 1 ? '0' + hex : hex
        }
        return `#${toHex(nVerm.value)}${toHex(nVerde.value)}${toHex(nAzul.value)}`
    })
   </script>

<style scoped>
.cor {
     width: 120px;
     height: 120px; 
     border: 1px solid #ccc; 
     margin-top: 20px;
     margin: auto;
}


</style>