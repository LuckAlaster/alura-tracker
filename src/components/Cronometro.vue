<template>
  <section>
    <strong class="display">
      {{ tempoDecorrido }} 
    </strong>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Cronometro-tempo",
  props: {
    tempoEmSegundos: {
        type: null,
        defaut: 0,
        
    }
  },
  computed: {
    tempoDecorrido(): string {
      return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11, 8);
    }
  },
})
</script>

<style>
  .display{
    color: var(--texto-primario);
  }
</style>