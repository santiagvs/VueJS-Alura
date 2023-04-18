<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
        />
      </div>
      <div class="column">
        <Temporizador />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Temporizador from "./Temporizador.vue";

export default defineComponent({
  name: "FormularioApp",
  components: {
    Temporizador,
  },
  data() {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
    };
  },
  methods: {
    iniciar() {
      this.cronometro = setInterval(() => {
        this.tempoEmSegundos++;
      }, 1000);
      console.log("iniciando");
    },
    finalizar() {
      clearInterval(this.cronometro);
    },
  },
});
</script>
