<template>
  <h2>{{title}}</h2>
  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ model }}</p>
  <p>Color: 
    <!-- <span v-for="(color, index) in colors" :key="index">
        {{index}}:{{color}} - 
    </span> -->
  </p>
  <ul>
    <li v-for="(color, index) in colors" :key="index">
        {{index}}:{{color}}
    </li>
  </ul>
  <p>Precio: {{ price }}$</p>
  <p>Potencia: {{power}}</p>
  <button @click="upPower(100)">Aumentar</button>
  <button @click="downPower(200)">Disminuir</button>
  <p>Potencias Urbanas menor a 300 cv</p>
  <ul>
    <!-- <li v-for="(power, index) in powers" :key="index"></li>
    <template v-if="power < 300">
        {{power}}
    </template>  -->

    <template v-for="(power, index) in powers" :key="index">
        <li v-if="power < 300">
            {{power}}
        </li>
    </template> 
  </ul>
  <p>Potencias Urbanas mayor a 300 cv</p>
  <ul>
    <template v-for="(power, index) in powers" :key="index">
        <li v-if="power > 300">
            {{power}}
        </li>
    </template> 
  </ul>
  <p>Potencias</p>
  <ul>
    <template v-for="(power, index) in powers" :key="index">
        <li v-if="power < 280">Urbana: {{power}}</li>
        <li v-else-if="power === 280">Hibrido: {{power}}</li>
        <li v-else>Carrera: {{power}}</li>

        <li v-if="power === 500">Super: {{power}}</li>
    </template> 
  </ul>
  {{message.title}} - {{message.text}}
</template>

<script>

export default {
 //Composition API
 setup(){
    const title = "Car - Composition API";
    const brand = "Audi";
    const model = "A4";
    const colors = ["Azul", "Rojo", "Verde"];
    const price = 38000;
    const power = 21;
    const powers = [60, 80, 120, 160, 200, 280, 300, 390, 540, 500];
    const message = {
            title: "Hola Mundo",
            text: "Adios",
        };
    const upPower = (newPower) => {
      console.log("Aumentar Potencia" +newPower);
    }; 
    const downPower = (newPower) => {
      console.log("Disminuir Potencia" +newPower);
    };
    return{
        title, 
        brand, 
        model, 
        colors, 
        price, 
        power,
        powers, 
        message,
        upPower,
        downPower,
    };
 },
};
</script>

<style>

</style>