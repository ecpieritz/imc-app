<template>
  <div id="app">
    <h1>Cálculo do IMC</h1>
    <h2>Digite seu peso e altura para calcular o IMC</h2>
    <div class="div-imc">
      <span class="p-float-label">
        <InputText id="input-weight" type="text" v-model="weight" />
        <label for="input-weight">Peso</label>
      </span>
    </div>

    <div class="div-imc">
      <span class="p-float-label">
        <InputText id="input-height" type="text" v-model="height" />
        <label for="input-height">Altura</label>
      </span>
    </div>

    <div class="div-imc">
      <Button label="Calcular" @click="calculate" />
    </div>

    <h3>Seu imc é de: {{imc}}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      height: null,
      weight: null,
      imc: null
    };
  },
  methods:{
    calculate(){
      this.imc = ((this.weight) / (this.height * this.height)).toFixed(2)
      return this.imc
    }
  }
};
</script>

<style>

</style>
