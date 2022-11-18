<template>
    <div class="formulario">
      <div class="formulario-title">{{title}}</div>
      <input v-model="inputValue" class="formulario-input" type="text">
    <button :disabled="inputValue.length===0" v-on:click="onSunmite">{{nomeButton}}</button>
    </div>
</template>

<script>
export default {
  name: 'FormularioForca',
  props:{
    title: String,
    nomeButton: String,
    action: Function

  },
  data(){
    return {
      inputValue:"",
      ativarButton: true
    }
  },
  methods:{
    onSunmite(){
      this.action(this.inputValue)
      this.inputValue=""
      
    }
  }
  
}
</script>
<style>
.formulario{
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
  margin-top: 20px;
}
.formulario-input{
  padding: 10px 5px;
  border: 0;
  border-radius: 5px;
  margin: 10px 0;
  text-align: center;
  color: var(--color-text-dark);
  font-size: 16px;
}
</style>