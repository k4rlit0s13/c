<template>
  <div>
    <h1>¡Diviértete con Vue!</h1>
    <div>
      <button @click="saludarAmigos">👋 Saludar Amigos</button>
      <button @click="buscarNumeroMenor">🔍 Encontrar Número Mínimo</button>
      <button @click="calcularSuma">➕ Sumar Números</button>
      <button @click="buscarValor">🔎 Buscar Valor</button>
      <button @click="encontrarPosicion">📍 Encontrar Posición</button>
      <button @click="verificarSamYFrodo">🧑‍🌾 Sam y Frodo</button>
      <button @click="contarDelicias">🍏 Contar Delicias</button>
    </div>
    <p v-if="resultado">{{ resultado }}</p>
  </div>
</template>

<style>
body {
  font-family: 'Comic Sans MS', cursive, sans-serif;
  background-color: #f0f8ff;
}
button {
  margin: 5px;
  padding: 10px;
  font-size: 16px;
  cursor: pointer;
  border-radius: 5px;
  background-color: #ffcc00;
  border: none;
}
button:hover {
  background-color: #ffdd57;
}
</style>

<script>
export default {
  data() {
    return {
      resultado: ''
    };
  },
  methods: {
    // Ejercicio 1: Saludar amigos
    saludarAmigos() {
      let amigos = prompt("Ingrese nombres de amigos separados por espacios:").split(" ");
      this.resultado = amigos.map(amigo => `¡Hola ${amigo}! 🎉`).join(' ');
    },
    
    // Ejercicio 2: Encontrar el número mínimo
    buscarNumeroMenor() {
      let numeros = prompt("Ingrese números separados por espacios:").split(" ").map(Number);
      let numeroMenor = Math.min(...numeros);
      this.resultado = `El número más pequeño es: ${numeroMenor} 🌟`;
    },
    
    // Ejercicio 3: Sumar números
    calcularSuma() {
      let numeros = prompt("Ingrese números separados por espacios:").split(" ").map(Number);
      let suma = numeros.reduce((acc, num) => acc + num, 0);
      this.resultado = `La suma total es: ${suma} 💰`;
    },
    
    // Ejercicio 4: Buscar un valor en una lista
    buscarValor() {
      let valores = prompt("Ingrese valores separados por espacios:").split(" ");
      let valorBuscado = prompt("Ingrese el valor a buscar:");
      this.resultado = valores.includes(valorBuscado)
        ? `El valor ${valorBuscado} está en la lista 📍`
        : `El valor ${valorBuscado} NO se encuentra en la lista ❌`;
    },
    
    // Ejercicio 5: Encontrar la posición de un valor
    encontrarPosicion() {
      let valores = prompt("Ingrese valores separados por espacios:").split(" ");
      let valorBuscado = prompt("Ingrese el valor a buscar:");
      let indice = valores.indexOf(valorBuscado);
      this.resultado = indice !== -1
        ? `El valor ${valorBuscado} está en la posición ${indice} 🔍`
        : `El valor ${valorBuscado} NO se encontró 🚫`;
    },
    
    // Ejercicio 6: Verificar si Sam y Frodo están juntos
    verificarSamYFrodo() {
      let nombres = prompt("Ingrese nombres separados por espacios:").split(" ");
      let samIndex = nombres.indexOf('Sam');
      let frodoIndex = nombres.indexOf('Frodo');
      this.resultado = Math.abs(samIndex - frodoIndex) === 1
        ? "¡Sam y Frodo están juntos! 🌈"
        : "¡Sam y Frodo están separados! 😱";
    },
    
    // Ejercicio 7: Contar diferentes frutas
    contarDelicias() {
      let frutas = prompt("Ingrese frutas separadas por espacios (use 🍎 para manzana, 🍐 para pera, 🍑 para durazno):").split(" ");
      let manzanas = frutas.filter(f => f === '🍎').length;
      let peras = frutas.filter(f => f === '🍐').length;
      let duraznos = frutas.filter(f => f === '🍑').length;
      this.resultado = `Hay ${manzanas} 🍎, ${peras} 🍐 y ${duraznos} 🍑 en total.`;
    },
    
  }
};
</script>
