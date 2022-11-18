<template>
  <div id="app">
    <h1>Jogo da forca</h1>
    <section v-if="tela" id="inicio">
      <Formulario
        v-if="etapa"
        title="Defina a palavra"
        nomeButton="Próximo"
        :action="setPalavra"
      />
      <Formulario
        v-else
        title="Defina a Dica"
        nomeButton="Iniciar jogo :)"
        :action="setEtapa"
      />
    </section>
    <section v-else id="jogo">
      <Jogo :erros="erros" />
    </section>
  </div>
</template>

<script>
import "./css/global.css";
import Formulario from "./components/form.vue";
import Jogo from "./components/jogo.vue";

export default {
  name: "App",
  data: function () {
    return {
      tela: true,
      etapa: true,
      palavra: "",
      dica: "",
      erros: 2,
    };
  },
  components: {
    Formulario,
    Jogo,
  },
  methods: {
    setPalavra(palavra) {
      this.palavra = palavra;
      this.etapa = false;
    },
    setEtapa(palavra) {
      //armazenar a dica
      this.dica = palavra;
      this.tela = false;
    },
  },
};
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
