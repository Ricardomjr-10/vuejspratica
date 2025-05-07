<template>
    <div>
        <h1>Lista de Tarefas Simples</h1>
        <input type="text" v-model="texto" placeholder="digite um nova tarefa" @keyup.enter="adicionar">
        <button @click="adicionar">Adicionar</button>
        <ul>
            <li v-for="(lista, index) in listas" :key="index">{{ lista }}</li>
        </ul>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const texto = ref('')
    const listas = ref([])

    const adicionar = () => {
        if (texto.value === '') {
            alert('Digite alguma coisa')
            return
        }

        listas.value.push(texto.value)
        texto.value = ''
    }

</script>

<style>
li {
    list-style: none;
}
</style>