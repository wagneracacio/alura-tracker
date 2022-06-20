<template >
    <Box>
        <div class="columns">
            <div class="column is-4">
                {{tarefa.descricao || 'Tarefa sem descrição'}}
            </div>
            <div class="column is-3">
                {{ tarefa.projeto?.nome || 'N/D'}}
            </div>
            <div class="column">
                <Cronomentro :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </Box>
</template>
<script lang="ts">
import ITarefa from '../interfaces/ITarefa'
import { defineComponent, PropType } from 'vue'
import Cronomentro from './Cronomentro.vue'
import Box from './Box.vue'
export default defineComponent({
    name: 'Tarefa',
    components: {
        Cronomentro,
        Box
    },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
})
</script>
