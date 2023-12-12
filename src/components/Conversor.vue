<template>
    <section class="cel:flex cel:items-center cel:justify-center cel:flex-col cel:w-full
    sm:flex sm:items-center sm:justify-center sm:flex-col sm:w-full
    md:flex md:items-center md:justify-center md:flex-col md:w-full
    lg:flex lg:items-center lg:justify-center lg:flex-col lg:w-full
    xl:flex xl:items-center xl:justify-center xl:flex-col xl:w-full
    2xl:flex 2xl:items-center 2xl:justify-center 2xl:flex-col 2xl:w-full
    ">
      <div class="cel:w-full cel:h-20 cel:grid cel:place-items-center
      sm:w-full sm:h-20 sm:grid sm:place-items-center
      md:w-full md:h-20 md:grid md:place-items-center
      lg:w-full lg:h-20 lg:grid lg:place-items-center
      xl:w-full xl:h-20 xl:grid xl:place-items-center
      2xl:w-full 2xl:h-20 2xl:grid 2xl:place-items-center
      ">
        <h1 class="text-white cel:text-3xl sm:text-3xl font-semibold md:text-4xl lg:text-5xl xl:text-5xl 2xl:text-5xl">CONVERSOR</h1>
      </div>
      <div class="cel:w-full cel:flex cel:flex-col cel:justify-center cel:items-center
      sm:w-full sm:flex sm:flex-col sm:justify-center sm:items-center
      md:w-full md:flex md:flex-col md:justify-center md:items-center
      lg:w-full lg:flex lg:flex-col lg:justify-center lg:items-center
      xl:w-full xl:flex xl:flex-col xl:justify-center xl:items-center
      2xl:w-full 2xl:flex 2xl:flex-col 2xl:justify-center 2xl:items-center
      ">
        <label for="numeroCambioDolar" class="text-white cel:mt-5 cel:mb-2 cel:font-thin cel:text-sm
        sm:mt-5 sm:mb-2 sm:font-normal sm:text-base
        md:mt-5 md:mb-2 md:font-medium md:text-lg
        lg:mt-5 lg:mb-2 lg:font-medium lg:text-lg
        xl:mt-5 xl:mb-2 xl:font-medium xl:text-lg
        2xl:mt-5 2xl:mb-2 2xl:font-medium 2xl:text-lg
        ">Dolares</label>
        <input type="number" name="numeroCambioDolar" id="numeroCambioDolar" inputmode="numeric"
          class="cel:w-3/4 cel:h-8 cel:border-none cel:mb-5 cel:text-center cel:text-black
          sm:w-3/4 sm:h-8 sm:border-none sm:mb-5 sm:text-center sm:text-black
          md:w-3/4 md:h-8 md:border-none md:mb-5 md:text-center md:text-black
          lg:w-3/4 lg:h-8 lg:border-none lg:mb-5 lg:text-center lg:text-black
          xl:w-3/4 xl:h-8 xl:border-none xl:mb-5 xl:text-center xl:text-black
          2xl:w-3/4 2xl:h-8 2xl:border-none 2xl:mb-5 2xl:text-center 2xl:text-black
          ">
      </div>
      <div class="cel:w-full cel:flex cel:flex-col cel:justify-center cel:items-center
      sm:w-full sm:flex sm:flex-col sm:justify-center sm:items-center
      md:w-full md:flex md:flex-col md:justify-center md:items-center
      lg:w-full lg:flex lg:flex-col lg:justify-center lg:items-center
      xl:w-full xl:flex xl:flex-col xl:justify-center xl:items-center
      2xl:w-full 2xl:flex 2xl:flex-col 2xl:justify-center 2xl:items-center
      ">
        <label for="selectDolar" class="cel:text-white cel:mt-5 cel:mb-2 cel:font-thin cel:text-sm
        text-white sm:mt-5 sm:mb-2 sm:font-normal sm:text-base
          md:mt-5 md:mb-2 md:font-medium md:text-lg
          lg:mt-2 lg:mb-2 lg:font-medium lg:text-lg
          xl:mt-2 xl:mb-2 xl:font-medium xl:text-lg
          2xl:mt-2 2xl:mb-2 2xl:font-medium 2xl:text-lg
          ">Seleccionar Dolar</label>
        <select v-model="tipoDolar" name="selectDolar" id="selectDolar"
          class="cel:w-3/4 cel:h-8 cel:border-none cel:mb-5 cel:text-center cel:text-black cel:overflow-y-auto
          sm:w-3/4 sm:h-8 sm:border-none sm:mb-5 sm:text-center sm:text-black sm:overflow-y-auto
          md:w-3/4 md:h-8 md:border-none md:mb-5 md:text-center md:text-black md:overflow-y-auto
          lg:w-3/4 lg:h-8 lg:border-none lg:mb-5 lg:text-center lg:text-black lg:overflow-y-auto
          xl:w-3/4 xl:h-8 xl:border-none xl:mb-5 xl:text-center xl:text-black xl:overflow-y-auto
          2xl:w-3/4 2xl:h-8 2xl:border-none 2xl:mb-5 2xl:text-center 2xl:text-black 2xl:overflow-y-auto
          ">
          <option class="cel:text-xs cel:max-h-16" v-for="tipo in dolares" :key="tipo.id" :value="tipo.venta">{{ tipo.casa
          }} - venta</option> 
        </select>
      </div>
      <div class="cel:w-full cel:flex cel:flex-col cel:justify-center cel:items-center
      sm:w-full sm:flex sm:flex-col sm:justify-center sm:items-center
      md:w-full md:flex md:flex-col md:justify-center md:items-center
      lg:w-full lg:flex lg:flex-col lg:justify-center lg:items-center
      xl:w-full xl:flex xl:flex-col xl:justify-center xl:items-center
      2xl:w-full 2xl:flex 2xl:flex-col 2xl:justify-center 2xl:items-center
      ">
        <label for="resultado" class="cel:text-white cel:mt-5 cel:mb-2 cel:font-thin cel:text-sm
        text-white sm:mt-5 sm:mb-2 sm:font-normal sm:text-base
          md:mt-5 md:mb-2 md:font-medium md:text-lg
          lg:mt-5 lg:mb-2 lg:font-medium lg:text-lg
          xl:mt-5 xl:mb-2 xl:font-medium xl:text-lg
          2xl:mt-5 2xl:mb-2 2xl:font-medium 2xl:text-lg
          ">Cambio a pesos
          argentinos</label>
        <input type="text" name="resultado" id="resultado" v-model="resultado" disabled
          class="cel:w-3/4 cel:h-8 cel:border-none cel:mb-5 cel:text-center cel:text-white text-center
          sm:w-3/4 sm:h-8 sm:border-none sm:mb-5 sm:text-center sm:text-white
          md:w-3/4 md:h-8 md:border-none md:mb-5 md:text-center md:text-white
          lg:w-3/4 lg:h-8 lg:border-none lg:mb-5 lg:text-center lg:text-white
          xl:w-3/4 xl:h-8 xl:border-none xl:mb-5 xl:text-center xl:text-white
          2xl:w-3/4 2xl:h-8 2xl:border-none 2xl:mb-5 2xl:text-center 2xl:text-white
          
          ">
      </div>
      <button type="submit" @click="capturarInputs" class="cel:w-40 cel:h-12 cel:bg-white cel:rounded-full cel:mt-5
      sm:w-40 sm:h-12 sm:bg-white sm:rounded-full sm:mt-5
      md:w-40 md:h-12 md:bg-white md:rounded-full md:mt-5
      lg:w-40 lg:h-12 lg:bg-white lg:rounded-full lg:mt-5
      xl:w-40 xl:h-12 xl:bg-white xl:rounded-full xl:mt-5
      2xl:w-40 2xl:h-12 2xl:bg-white 2xl:rounded-full 2xl:mt-5
      mb-3
      ">CONVERTIR</button>
    </section>
  </template>
    
  <script>
  import axios from 'axios';
  
  export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Conversor',
    data() {
      return {
        dolares: [],
        resultado: ""
      };
    },
    methods: {
      capturarInputs() {
        const cambioDolar = document.getElementById('numeroCambioDolar');
        const valorCambioDolar = Number(cambioDolar.value);
  
        const cambioSelectDolar = document.getElementById('selectDolar');
        const valorSelectDolar = Number(cambioSelectDolar.value);
  
        let resultadoNumerico = valorCambioDolar * valorSelectDolar;
  
        this.resultado = '$' + resultadoNumerico.toLocaleString();
        console.log(this.resultado);
      }
    },
    mounted() {
      let vue = this;
      axios
        .get('https://dolarapi.com/v1/dolares')
        .then(function (response) {
          vue.dolares = response.data;
          console.log(vue.dolares)
        })
    }
  }
  </script>
    
    <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style></style>
    