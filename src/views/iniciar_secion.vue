<template>
    <div class="container" >
      <h1>Iniciar Sesión</h1>
      <form @submit.prevent="login">
        <label for="username">Nombre de usuario:</label>
        <input type="text" id="username" v-model="username">
        <label for="password">Contraseña:</label>
        <input type="password" id="password" v-model="password">
        <button type="submit">Iniciar Sesión</button>
      </form>
      <div v-if="error" class="error">{{ error }}</div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        username: '',
        password: '',
        error: ''
      };
    },
    methods: {
      login() {
        // Realizar la lógica de inicio de sesión aquí, como enviar una solicitud a un servidor API
        
        // Ejemplo de verificación básica
        if (this.username === 'admin' && this.password === 'password') {
          // Inicio de sesión exitoso
          this.error = '';
          alert('Inicio de sesión exitoso');
          // Aquí puedes redirigir al usuario a otra página después del inicio de sesión
        } else {
          // Credenciales incorrectas
          this.error = 'Credenciales incorrectas. Inténtalo de nuevo.';
        }
      }
    }
  };
  </script>
  
  <style>
  .error {
    color: red;
    margin-top: 10px;
  }
  .container{
    display: flex-start;
    align-content:center;
    
  }
  </style>
  