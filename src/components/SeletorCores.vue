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
        <button @click="copiarHex">Copiar Hex</button>
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

    const copiarHex = () => {
        navigator.clipboard.writeText(hexColor.value)
        .then(() => {
            alert('Codigo hexadecimal copiado para area de transferencia!')
        })
        .catch( err => {
            console.error('Falha ao copiar para area de transferencia: ', err)
            alert('Não foi possivel copiar para area de transferencia.')
        })
    }
   </script>

<style scoped>
div {
    text-align: center;
    font-family: Arial, sans-serif;
}

h1 {
    color: #333;
    margin-bottom: 20px;
}

label {
    font-weight: bold;
    margin-right: 10px;
}

input[type="number"] {
    width: 60px;
    padding: 5px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

button {
    background-color: #4CAF50;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
    font-size: 14px;
}

button:hover {
    background-color: #45a049;
}

p {
    font-size: 16px;
    color: #555;
}
.cor {
     width: 120px;
     height: 120px; 
     border: 1px solid #ccc; 
     margin-top: 20px;
     margin: auto;
}


</style>