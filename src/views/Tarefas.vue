<template>
    <Formulario @aoSalvarTarefa="salvarTarefa" />
    <div class="lista m-3">
        <Tarefa v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        <Box id="box" v-if="listaEstaVazia"> Crie sua primeira tarefa para iniciamos 😁</Box>
    </div>
</template>


<script lang="ts">
import { defineComponent } from 'vue';
import Formulario from '../components/Formulario.vue';
import Tarefa from '../components/Tarefa.vue';
import ITarefa from '../interfaces/ITarefa';
import Box from '../components/Box.vue';

export default defineComponent({
    name: 'TarefasView',
    components: {
        Formulario,
        Tarefa,
        Box
    },
    data () {
        return {
            tarefas: [] as ITarefa[]
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
    }
});
</script>