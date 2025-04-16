<template>
   <header>
      <h1>
         <img src="../assets/logo.png" alt="">
      </h1>
      <button class="button" @click="alterarTema"> {{ textoBotao }}</button>
      <nav class="panel mt-5">
         <ul>
            <li>
               <RouterLink to="/" class="link">
                  <i class="fas fa-tasks"></i>
                  Tarefas
               </RouterLink>
            </li>
            <li>
               <RouterLink to="/projetos" class="link">
                  <i class="fas fa-project-diagram"></i>
                  Projetos
               </RouterLink>
            </li>
         </ul>
      </nav>
   </header>
</template>

<script lang="ts">
import { defineComponent, DefineComponent } from 'vue';

export default defineComponent({
   name: 'BarraLateral',
   emits: ['aoTemaAlterado'],
   data () {
      return {
         modoEscuroAtivo: false
      }
   },
   computed: {
      textoBotao () {
         if (!this.modoEscuroAtivo) {
            return 'Tema Claro'
         } 
         return 'Tema Escuro'
      }
   },
   methods: {
      alterarTema () {
         this.modoEscuroAtivo = !this.modoEscuroAtivo
         this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
      }
   }
});
</script>

<style scoped>

   header {
      padding: 1rem;
      background: #0d3b66;
      width: 100%;
      height: 100vh;
      text-align: center;
   }

   @media only screen and (max-width: 768px) {
      header {
         padding: 2.5rem;
         height: auto;
      }
   }

   .panel {
      background-color: #00000000;
      border: none;
      box-shadow: none;
      display: flex;
      justify-content: baseline;
      padding: 0 0 0 1%;
   }

   .panel li {
      margin: 8px 0;
   }

   .link {
      color: #fff;
   }

   .link:hover, .link.router-link-active {
      color: #faf0ca;
   }


</style>