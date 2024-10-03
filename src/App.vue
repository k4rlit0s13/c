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
      <button @click="comidaDeMonos">🍌 Comida para Monos</button>
      <button @click="organizarAnimales">🐶🐱 Organizar Animales</button>
      <button @click="germinarFlores">🌸 Germinación de Flores</button>
      <button @click="recortarPalabras">✂️ Recortar Palabras</button>
      <button @click="multiplicarNumeros">✖️ Multiplicar Números</button>
      <button @click="exterminarInsectos">🦟 Exterminar Insectos</button>
      <button @click="compararArrays">📊 Comparar Arrays</button>
      <button @click="puntajesJuego">🏆 Puntajes del Juego</button>
      <button @click="piedraPapelTijera">✋ Piedra, Papel o Tijera</button>
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

    // Ejercicio 8: Comida para monos
    comidaDeMonos() {
      let elementos = prompt("Ingrese monos (🐵) y bananas (🍌):").split("");
      let monos = elementos.filter(e => e === '🐵').length;
      let bananas = elementos.filter(e => e === '🍌').length;
      let bananasPorMono = prompt("¿Cuántas bananas come un mono?:");
      this.resultado = bananas >= monos * bananasPorMono
        ? "¡Hay suficientes bananas para los monos! 🍌"
        : "¡Oh no! ¡No hay suficientes bananas para los monos! 😭";
    },

    // Ejercicio 9: Organizar animales
    organizarAnimales() {
      let animales = prompt("Ingrese perros (🐶) y gatos (🐱):").split("");
      let perros = animales.filter(a => a === '🐶').join('');
      let gatos = animales.filter(a => a === '🐱').join('');
      this.resultado = `Resultado: ${perros}${gatos}`;
    },

    // Ejercicio 10: Germinación de flores
    germinarFlores() {
      let plantas = prompt("Ingrese flores (🌼) y plantines (🌱):");
      let resultado = ""; // Variable para almacenar el resultado final
      let flor = ""; // Variable para almacenar la última flor encontrada

      // Recorremos cada caracter de la entrada
      for (let i = 0; i < plantas.length; i++) {
        if (plantas[i] !== '🌱') {
          flor = plantas[i]; // Guardamos la flor actual
          resultado += flor; // Agregamos la flor al resultado
        } else {
          resultado += flor; // Reemplazamos 🌱 por la última flor
        }
      }

      this.resultado = `¡Las flores han germinado! 🌸: ${resultado}`;
    },

    // Ejercicio 11: Recortar palabras
    recortarPalabras() {
      let palabras = prompt("Ingrese palabras separadas por espacios:").split(" ");
      let caracteresPermitidos = prompt("Ingrese cantidad de caracteres permitidos:");
      let recortadas = palabras.map(palabra => palabra.substring(0, caracteresPermitidos));
      this.resultado = `Las palabras recortadas son: ${recortadas.join(" ")}`;
    },

    // Ejercicio 12: Multiplicar números individuales
    multiplicarNumeros() {
      let numeros = prompt("Ingrese números separados por espacios:").split(" ").map(Number);
      let multiplicador = prompt("Ingrese multiplicador:");
      let resultado = numeros.map(num => num * multiplicador);
      this.resultado = `El array resultante es: [${resultado}]`;
    },

    // Ejercicio 13: Exterminar insectos
    exterminarInsectos() {
      let animales = prompt("Ingrese animales:").split(" ");
      let sinInsectos = animales.filter(animal => animal !== '🦟' && animal !== '🦂');
      this.resultado = `Animales sin insectos: [${sinInsectos.join(', ')}]`;
    },

    // Ejercicio 14: Comparar arrays
    compararArrays() {
      let lista1 = prompt("Ingrese valores de lista 1:").split(" ");
      let lista2 = prompt("Ingrese valores de lista 2:").split(" ");
      this.resultado = JSON.stringify(lista1) === JSON.stringify(lista2)
        ? "Las listas son iguales"
        : "Las listas no son iguales";
    },

    // Ejercicio 15: Puntajes del juego
    puntajesJuego() {
      let nombre1 = prompt("Ingrese nombre jugadora 1:");
      let puntajes1 = prompt(`Ingrese puntajes de ${nombre1}:`).split(" ").map(Number);
      let nombre2 = prompt("Ingrese nombre jugadora 2:");
      let puntajes2 = prompt(`Ingrese puntajes de ${nombre2}:`).split(" ").map(Number);
      let suma1 = puntajes1.reduce((a, b) => a + b, 0);
      let suma2 = puntajes2.reduce((a, b) => a + b, 0);
      this.resultado = `${nombre1} tiene ${suma1} puntos y ${nombre2} tiene ${suma2} puntos.`;
    },

    // Ejercicio 16: Piedra, papel o tijera
    piedraPapelTijera() {
      let opciones = ['piedra', 'papel', 'tijera'];
      let jugador1 = prompt("Jugador 1, elija piedra, papel o tijera:");
      let jugador2 = prompt("Jugador 2, elija piedra, papel o tijera:");

      if (jugador1 === jugador2) {
        this.resultado = "¡Es un empate! 🤝";
      } else if (
        (jugador1 === 'piedra' && jugador2 === 'tijera') ||
        (jugador1 === 'papel' && jugador2 === 'piedra') ||
        (jugador1 === 'tijera' && jugador2 === 'papel')
      ) {
        this.resultado = "¡Jugador 1 gana! 🎉";
      } else {
        this.resultado = "¡Jugador 2 gana! 🎊";
      }
    }
  }
};
</script>
