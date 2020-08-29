<template>
<div id="app">
  <h2>-- Cuenta Regresiva --</h2>
  <h1>00:{{contadorSeg < 10 ? '0'+contadorSeg : contadorSeg }} /seg</h1>
  <div class="botones">
    <button @click="iniciar(5)">5 seg</button>
    <button @click="iniciar(10)">10 seg</button>
    <button @click="iniciar(30)">30 seg</button>
    <button @click="iniciar(60)">60 seg</button>
  </div>
</div>
</template>

<script>
export default {
  name: "Countdown",

  data() {
    return {
      contadorSeg: 0,
      myIntervalo: null,
    };
  },

  methods: {
    iniciar(time) {
      this.contadorSeg = time;
      clearInterval(this.myIntervalo);
      this.myIntervalo = setInterval(() => {
        this.contadorSeg > 0 ? this.contadorSeg-- : clearInterval(this.myIntervalo);
      }, 1000);
    },
  },
};
</script>

<style lang="scss">
body{
  background-color: #f5f5f5;
  display: flex;
  justify-content: center;
}
#app {
  width: 500px;
  text-align: center;
  background-color: #e0e0e0;
  color: #2c3e50;
  padding: 30px 0 50px 0;
  margin-top: 60px;
  font-family: 'Aldrich', sans-serif;
  box-shadow: 10px 10px 5px -8px rgba(158,156,158,1);
  border-radius: 3px;

 button{
   font-family: 'Aldrich', sans-serif;
   margin: 5px;
   background-color: #2c3e50;
   color: white;
   border-radius: 2px;

 }
}
</style>
