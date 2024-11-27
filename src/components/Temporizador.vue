<template>
   <div class="is-flex is-align-items-center is-justify-content-space-between">
      <Cronometro :tempo-em-segundos="tempoEmSegundos"/>
      <button class="button mr-3" @click="iniciar" :disabled="cronometroRodando">
         <span class="icon">
            <i class="fas fa-play"></i>
         </span>
         <span>play</span>
      </button>
      <button class="button mr-3" @click="finalizar" :disabled="!cronometroRodando">
         <span class="icon">
            <i class="fa-solid fa-pause"></i>
         </span>
         <span>stop</span>
      </button>
   </div>
</template>

<script lang="ts">

   import { defineComponent, DefineComponent } from 'vue';
   import Cronometro from './Cronometro.vue';

   export default defineComponent({
      name: 'TemporizadorTempo',
      components: {
         Cronometro
      },
      data () {
         return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false
         }
      },
      methods: {
         iniciar () {
            this.cronometro = setInterval(() => {
               this.tempoEmSegundos += 1
            }, 1000)
            this.cronometroRodando = true
         },
         finalizar () {
            clearInterval(this.cronometro);
            this.cronometroRodando = false
         }
      }
   });

</script>

<style scoped>

</style>