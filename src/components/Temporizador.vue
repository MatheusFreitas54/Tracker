<template>
   <div class="is-flex is-align-items-center is-justify-content-space-between">
      <Cronometro :tempo-em-segundos="tempoEmSegundos"/>
      <Botao @click="iniciar" :disabled="cronometroRodando" :texto="'play'" :icone="`<i class=\'fas fa-play\'></i>`" />
      <Botao @click="finalizar" :disabled="!cronometroRodando" :texto="'stop'" :icone="`<i class=\'fa-solid fa-pause\'></i>`" />
   </div>
</template>

<script lang="ts">

   import { defineComponent} from 'vue';
   import Cronometro from './Cronometro.vue';
   import Botao from './Botao.vue';

   export default defineComponent({
      name: 'TemporizadorTempo',
      emits: ['aoTemporizadorFinalizado'],
      components: {
         Cronometro, Botao
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
            this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos)
            this.tempoEmSegundos = 0
         }
      }
   });

</script>

<style scoped>

</style>