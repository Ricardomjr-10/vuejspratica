<template>
    <div>
        <h1>Mensagem Personalizada</h1>
         <label for="nome">Nome: </label>
         <input type="text" v-model="nome" placeholder="Digite seu nome" />
         <div>{{ nome }}</div>
    </div>
</template>

<script setup>

</script>