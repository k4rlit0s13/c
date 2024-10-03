<template>
  <div>
    <h1>¡Diviértete con Vue!</h1>
    <div>
      <button @click="saludarAmigos">👋 Saludar Amigos</button>
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
    
}
};
</script>
