<template>
  <section class="cel:flex cel:items-center cel:justify-center cel:flex-col cel:w-full
  sm:flex sm:items-center sm:justify-center sm:flex-col sm:w-full
  md:flex md:items-center md:justify-center md:flex-col md:w-full
  lg:flex lg:items-center lg:justify-center lg:flex-col lg:w-full
  xl:flex xl:items-center xl:justify-center xl:flex-col xl:w-full
 ">
      <div class="cel:w-full cel:h-20 cel:grid cel:place-items-center
      sm:w-full sm:h-20 sm:grid sm:place-items-center
      md:w-full md:h-20 md:grid md:place-items-center
      lg:w-full lg:h-20 lg:grid lg:place-items-center
      xl:w-full xl:h-20 xl:grid xl:place-items-center
      ">
        <h1 class="cel:text-white cel:text-3xl cel:font-semibold
        sm:text-white sm:text-3xl sm:font-semibold
        md:text-white md:text-5xl md:font-semibold
        lg:text-white lg:text-5xl lg:font-semibold
        xl:text-white xl:text-5xl xl:font-semibold
        ">DOLAR AHORA</h1>
      </div>
      <div class="cel:w-full cel:flex cel:flex-col cel:justify-center cel:items-center
      sm:w-full sm:flex sm:flex-col sm:justify-center sm:items-center
      md:w-full md:flex md:flex-wrap md:justify-center md:items-center
      lg:w-full lg:flex lg:flex-wrap lg:justify-center lg:items-center
      xl:w-full xl:flex xl:flex-wrap xl:justify-center xl:items-center
      ">
        <div class="cel:w-3/4 cel:h-56 cel:border-black cel:shadow-md cel:shadow-black cel:border-2 cel:rounded-2xl cel:bg-gray-900 cel:mt-5 cel:mb-5 cel:flex cel:flex-col cel:justify-center cel:items-center
        sm:w-3/4 sm:h-56 sm:border-black sm:shadow-md sm:shadow-black sm:border-2 sm:rounded-2xl sm:bg-gray-900 sm:mt-5 sm:mb-5 sm:flex sm:flex-col sm:justify-center sm:items-center
        md:w-64 md:ml-10 md:mr-10 md:h-56 md:border-black md:shadow-md md:shadow-black md:border-2 md:rounded-2xl md:bg-gray-900 md:mt-5 md:mb-5 md:flex md:flex-col md:justify-center md:items-center
        lg:w-72 lg:ml-10 lg:mr-10 lg:h-64 lg:border-black lg:shadow-md lg:shadow-black lg:border-2 lg:rounded-2xl lg:bg-gray-900 lg:mt-5 lg:mb-5 lg:flex lg:flex-col lg:justify-center lg:items-center
        xl:w-72 xl:ml-10 xl:mr-10 xl:h-64 xl:border-black xl:shadow-md xl:shadow-black xl:border-2 xl:rounded-2xl xl:bg-gray-900 xl:mt-5 xl:mb-5 xl:flex xl:flex-col xl:justify-center xl:items-center
        " v-for="tipos in dolares" :key="tipos.id">
            <h2 class= "uppercase text-white font-semibold sm:text-2xl md:text-2xl lg:text-2xl">{{ tipos.casa }}</h2>
            <div class="text-center cel:mt-2
            sm:text-center sm:mt-2 md:mt-3
            lg:text-center lg:mt-4
            xl:text-center xl:mt-4
            ">
              <h3 class="text-red-600">Venta</h3>
              <h3 class="text-red-600 font-semibold cel:text-2xl sm:text-2xl md:text-2xl lg:text-3xl xl:text-3xl">${{ tipos.venta }}</h3>
            </div>
            <div v-if="!tipos.compra == ''" class="text-center cel:mt-2 sm:mt-2 md:mt-3 lg:mt-4 xl:mt-4">
              <h3 class="text-green-600">Compra</h3>
              <h4 class="text-green-600 font-semibold cel:text-2xl sm:text-2xl md:text-2xl lg:text-3xl xl:text-3xl">${{ tipos.compra }}</h4>
            </div>
            <div class="text-center cel:mt-3 sm:mt-3">
                <h6 v-if="dolares.length > 0" class="cel:text-xs text-white sm:text-base  md:text-xs md:mt-1 md:mb-1 mt-2 mb-2 lg:text-sm xl:text-sm">Ultima actualización: {{
                    formatearFecha(dolares[0].fechaActualizacion) }}</h6>
            </div>
        </div>
      </div>
  </section>
</template>

<style></style>

<script>
import axios from 'axios';
import { DateTime } from "luxon";

export default {
  name: 'HelloWorld',
  data() {
    return {
      dolares: []
    }
  },
  methods: {
    formatearFecha(fecha) {
      const fechaFormateada = DateTime.fromISO(fecha, { zone: "America/Argentina/Buenos_Aires" });
      return fechaFormateada.toFormat("dd/MM/yyyy HH:mm:ss");
    },
  },
  mounted() {
    let vue = this;
    axios
      .get('https://dolarapi.com/v1/dolares')
      .then(function (response) {
        vue.dolares = response.data;
        //console.log(vue.dolares);
      })
  }



}

</script>