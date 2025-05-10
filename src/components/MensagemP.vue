<template>
    <div>
        <h1>Mensagem Personalizada</h1>
         <label for="nome">Nome: </label>
         <input type="text" v-model="nome" placeholder="Digite seu nome" />
         <p v-if="nome">Olá, {{ nome }}</p>
         <p v-else>Digite o nome acima</p>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const nome = ref('')
</script>

<style scoped>
div {
    font-family: Arial, sans-serif;
    text-align: center;
    margin-top: 20px;
}

h1 {
    color: #4CAF50;
    font-size: 24px;
    margin-bottom: 20px;
}

label {
    font-weight: bold;
    margin-right: 10px;
}

input {
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 14px;
}

p {
    margin-top: 10px;
    font-size: 16px;
}

p[v-if] {
    color: #4CAF50;
}

p[v-else] {
    color: #FF5722;
}

</style>