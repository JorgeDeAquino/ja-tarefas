<template>
    <section>
        <strong>
            {{ tempoDcorrido }}
        </strong>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'Cronometro',
    props: {
        tempoEmSugundos: {
            type: Number,
            default: 0
        }
    },
    computed: {
        tempoDcorrido () : string {
            return new Date(this.tempoEmSugundos * 1000).toISOString().substring(19,11)
        }
    },
})
</script>