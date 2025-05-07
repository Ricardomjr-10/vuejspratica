<template>
    <div>
        <h1>Texto Dinamico</h1>
        <input type="text" v-model="texto">
        <p>Digite o texto acima: {{ texto }}</p>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const texto = ref('')
    // export default {
    //     setup() {
    //         const texto = ref('')

    //         return {
    //             texto
    //         }
    //     }
    // }

</script>