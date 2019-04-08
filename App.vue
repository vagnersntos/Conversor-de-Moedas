<template>
  <div id="app">
    <h1>Conversor de Moedas</h1>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL"/>
      <Conversor moeda-a="BRL" moeda-b="USD"/>
    </div>

    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL"/>
      <Conversor moeda-a="BRL" moeda-b="EUR"/>
    </div>
      <div class="linha">
      <Conversor moeda-a="BTC" moeda-b="BRL"/>
      <Conversor moeda-a="BRL" moeda-b="BTC"/>
    </div>
    
  </div>
  
</template>

<script>
import Conversor from "./components/Conversor.vue";
export default {
  name: 'app',
  components: {
    Conversor
     }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #020202;
  margin-top: 60px;
}

.linha{
  margin-top: 40px;
  display: flex;
  justify-content: space-between;
}
</style>
