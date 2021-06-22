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

    <div>
      <h3>Seu imc é de: {{ imc }}</h3>
      <h4>A classificação do seu IMC é: <span class="text-blue">{{ classification }}</span></h4>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      height: null,
      weight: null,
      imc: null,
      classification: ''
    };
  },
  methods:{
    calculate(){
      this.imc = ((this.weight) / (this.height * this.height)).toFixed(2)
      
      if (this.imc < 18.5){
        this.classification = 'Magreza'
      } else if (this.imc >= 18.5 && this.imc < 25){
        this.classification = 'Normal'
      } else if (this.imc >= 25 && this.imc < 30){
        this.classification = 'Sobrepeso'
      } else if (this.imc >= 30 && this.imc < 40){
        this.classification = 'Obesidade'
      } else{
        this.classification = 'Obesidade Grave'
      }
    }
  }
};
</script>

<style>
</style>
