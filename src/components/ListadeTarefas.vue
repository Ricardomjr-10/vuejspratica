<template>
    <div>
        <h1>Lista de Tarefas Simples</h1>
        <input type="text" v-model="texto" placeholder="digite um nova tarefa" @keyup.enter="adicionar">
        <button @click="adicionar">Adicionar</button>
        <ul>
            <li v-for="(lista, index) in listas" :key="index">
                <span :class="{concluida: lista.concluida}">{{ lista.texto }}</span>
                 <button @click="concluida(index)">Concluida
                    {{ lista.concluida ? 'Desconcluir' : 'Concluir' }}
                 </button>
                 <button @click="remover(index)">Remover</button>
                </li>
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

        listas.value.push({texto:texto.value.trim(), concluida: false})
        texto.value = ''

    }
    const concluida = (index) => {
       listas.value[index].concluida = !listas.value[index].concluida
    }

    const remover = (index) => {
        listas.value.splice(index, 1)
    }
    
</script>

<style scoped>
.concluida {
  text-decoration: line-through;
  color: #888;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin-bottom: 8px;
  padding: 10px;
  border: 1px solid #eee;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

li span {
  flex-grow: 1;
  margin-right: 10px;
}

li button {
  margin-left: 5px;
}
</style>