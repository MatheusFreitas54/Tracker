<template>
   <button class="button mr-3" :disabled="disabled">
      <span class="icon" v-html="icone"></span>
      <span> {{ texto }}</span>
   </button>
</template>

<script lang="ts">

   import { defineComponent } from 'vue';

   export default defineComponent({
      name: 'BotaoTempo',
      props: {
         tempoEmSegundos: {
            type: Number,
            default: 0
         },
         texto: {
            type: String,
            default: ''
         },
         icone: {
            type: String,
            default: ''
         },
         disabled: {
            type: Boolean,
            default: false
         },
      },
      emits: ['aoTemporizadorFinalizado'],
      data () {
         return {
            cronometro: 0,
            cronometroRodando: false
         }
      }
   });

</script>