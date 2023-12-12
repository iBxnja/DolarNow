<template>
  <HelloWorld ></HelloWorld>
  <Conversor></Conversor>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Conversor from './components/Conversor.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Conversor
  }
}
</script>
<style>
*{
  padding: 0;
  margin: 0;
}
#app{
  width: 100%;
  height: 550vh;
  background: rgb(7,15,48);
  background: linear-gradient(90deg, rgba(7,15,48,1) 0%, rgba(20,37,112,1) 50%, rgba(7,15,48,1) 100%);
}
@media only screen and (min-width: 768px) and (max-width: 1023px) {
  #app{
  width: 100%;
  height: 340vh;
  }
}
@media only screen and (min-width: 1024px) and (max-width: 1279px){
  #app{
  width: 100%;
  height: 370vh;
  }
}
@media only screen and (min-width: 1280px) and (max-width: 1535px){
  #app{
  width: 100%;
  height: 220vh;
  }
}

</style>
