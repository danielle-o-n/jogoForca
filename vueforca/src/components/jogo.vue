<template>
  <div class="jogo">
    <Forca :erros="erros" />
  </div>
</template>

<script>
import Forca from "./forca.vue";
export default {
  name: "jogoForca",

  data() {
    return {};
  },
  props: {
    erros: Number,
  },
  components: {
    Forca,
  },
};
</script>
