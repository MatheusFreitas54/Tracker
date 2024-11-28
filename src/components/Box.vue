<template>
   <div class="box has-text-weight-bold" :style="estilos">
      <slot></slot>
   </div>
</template>

<script lang="ts">

   import { defineComponent, PropType} from 'vue';

   export default defineComponent({
      name: 'BoxTarefa',
      data () {
         return {
            estilos: {
               background: '#FAFOCA'
            }
         }
      }
   });

</script>

<style scoped>

   .box {
      background: #FAF0CA;
      color: #707070;
   }

</style>