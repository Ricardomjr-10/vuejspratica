<template>
  <ContadorTeste/>
  <TextoDinaminco/>
  <ListadeTarefas/>
  <SeletorCores/>
</template>

<script>
import ContadorTeste from './components/ContadorTeste'
import ListadeTarefas from './components/ListadeTarefas.vue';
import SeletorCores from './components/SeletorCores.vue';
import TextoDinaminco from './components/TextoDinaminco.vue';

export default {
  name: 'App',
  components: {
    ContadorTeste,
    TextoDinaminco,
    ListadeTarefas,
    SeletorCores
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
