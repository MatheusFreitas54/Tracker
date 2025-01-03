<template>
  <main class="columns is-gapless is-multiline" :class="{ 'dark-mode': modoEscuroAtivo }">
    <div class="column is-one-quarter">
      <BarraLateral @aoTemaAlterado="trocarTema"/>
    </div>
    <div class="column is-three-quarter content">
      <RouterView></RouterView>
    </div>
  </main>
</template>


<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral
  },
  data () {
    return {
      modoEscuroAtivo: true
    }
  },
  methods: {
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
