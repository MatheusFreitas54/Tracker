<template>
  <main class="columns is-gapless is-multiline" :class="{ 'dark-mode': modoEscuroAtivo }">
    <div class="column is-one-quarter">
      <BarraLateral @aoTemaAlterado="trocarTema"/>
    </div>
    <div class="column is-three-quarter content">
      <Formulario @aoSalvarTarefa="salvarTarefa" />
      <div class="lista m-3">
        <Tarefa v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        <Box id="box" v-if="listaEstaVazia"> Crie sua primeira tarefa para iniciamos 😁</Box>
      </div>
    </div>
  </main>
</template>


<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import Formulario from './components/Formulario.vue';
import Tarefa from './components/Tarefa.vue';
import ITarefa from './interfaces/ITarefa';
import Box from './components/Box.vue';

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    Formulario,
    Tarefa,
    Box
  },
  data () {
    return {
      tarefas: [] as ITarefa[],
      modoEscuroAtivo: true
    }
  },
  computed: {
    listaEstaVazia () : boolean {
      return this.tarefas.length === 0
    }
  },
  methods: {
    salvarTarefa (tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    },
    trocarTema (modoEscuroAtivo: boolean) {
      this.modoEscuroAtivo = !modoEscuroAtivo
    }
  }
});
</script>


<style>
  .lista {
    padding: 1.24rem;
  }

  #box {
    margin: 5px 50px;
    text-align: center;
  }

  main {
    --bg-primario: #fff;
    --texto-primario: #000;
  }

  main.dark-mode {
    --bg-primario: #2b2d42;
    --texto-primario: #ddd;
  }

  .content {
    background-color: var(--bg-primario);
  }
</style>
