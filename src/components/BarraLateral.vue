<template>
  <header>
    <h1>
      <img src="../assets/logoAluraTracker.png" alt="" />
    </h1>
    <button class="button" @click="alterarTema">
      <span class="icon">
        <i class="fa-solid fa-circle-half-stroke"></i>
      </span>
      <span>
        {{ textoDoBotaoDeTema }}
      </span>
    </button>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BarraLetral",
  emits: ["aoTemaAlterado"],
  data() {
    return {
      modoEscuroAtivo: false,
    };
  },
  computed: {
    textoDoBotaoDeTema() {
      return this.modoEscuroAtivo
        ? "Desativar modo escuro"
        : "Ativar modo escuro";
    },
  },
  methods: {
    alterarTema() {
      this.modoEscuroAtivo = !this.modoEscuroAtivo;
      this.$emit("aoTemaAlterado", this.modoEscuroAtivo);
    },
  },
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
header h1 {
  text-align: center;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
