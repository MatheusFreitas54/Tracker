<template>
   <section class="mr-3 ml-3">
      <strong> {{ tempoDecorrido }}</strong>
   </section>
</template>

<script lang="ts">
import { defineComponent, DefineComponent } from 'vue';

export default defineComponent({
   name: 'CronometroTempo',
   props: {
      tempoEmSegundos: {
         type: Number,
         default: 0
      }
   },
   computed: {
      tempoDecorrido () : string {
         return new Date(this.tempoEmSegundos * 1000).toISOString().substring(11,19);
      }
   },
});
</script>

<style scoped>

</style>