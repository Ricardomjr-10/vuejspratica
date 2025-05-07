<template>
    <div>
        <h1>Contador</h1>
        <div class="numero"> <button @click="decrementar">-</button> {{ numb }} <button @click="incrementar">+</button> </div>
    </div>
</template>

<script>
import { ref } from 'vue'

export default {
    setup() {
        const numb = ref(0)

        const decrementar = () => {
            numb.value--
        }

        const incrementar = () => {
            numb.value++
        }

        return {
            numb,
            decrementar,
            incrementar
        }
    }
    // data() {
    //     return {
    //         numb:0
    //     }
    // },

    // methods: {
    //     decrementar() {
    //         this.numb--
    //     },

    //     incrementar() {
    //         this.numb++
    //     }

    // }


}
</script>

<style scoped>
.numero {
    font-size: 40px;
}
button {
    font-size: 30px;
    font-weight: 700;
    cursor: pointer;
    border: none;
    background-color: white;
}
</style>