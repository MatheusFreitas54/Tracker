<template>
   <div class="box">
      <div class="columns">
         <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
            <input type="text" class="input" placeholder="Qual Tarefe você deseja iniciar?">
         </div>
         <div class="columns">
            <div class="is-flex is-align-items-center is-justify-content-space-between">
               <section class="mr-3 ml-3">
                  <strong>00:00:00</strong>
               </section>
               <button class="button mr-3">
                  <span class="icon">
                     <i class="fas fa-play"></i>
                  </span>
                  <span>play</span>
               </button>
               <button class="button mr-3">
                  <span class="icon">
                     <i class="fas fa-play"></i>
                  </span>
                  <span>stop</span>
               </button>
            </div>
         </div>
      </div>
   </div>
</template>

<script lang="ts">
   import { defineComponent, DefineComponent } from 'vue';

   export default defineComponent({
      name: 'FormularioCadastro'
   });
</script>

<style scoped>

</style>