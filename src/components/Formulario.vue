<template>
   <div class="box form">
      <div class="columns">
         <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
            <input type="text" class="input" placeholder="Qual Tarefa você deseja iniciar?" v-model="descricao">
         </div>
         <div class="columns">
            <Temporizador @ao-temporizador-finalizado="finalizarTarefa"/>
         </div>
      </div>
   </div>
</template>

<script lang="ts">
   import { defineComponent } from 'vue';
   import Temporizador from './Temporizador.vue';

   export default defineComponent({
      name: 'FormularioCadastro',
      emits: ['aoSalvarTarefa'],
      components: {
         Temporizador
      },
      data () {
         return {
            descricao: ''
         }
      },
      methods: {
         finalizarTarefa (tempoDecorrido : number) : void {
            this.$emit('aoSalvarTarefa', {
               duracaoEmSegundos: tempoDecorrido,
               descricao: this.descricao
            })
            this.descricao = ''
         }
      }
      
   });
</script>

<style>
   .form, .input, .input::placeholder {
      color: var(--texto-primario);
      background-color: var(--bg-primario);
   }

   .form {
      border-radius: 0;
      box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
   }

</style>