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
 .container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.login-form {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 300px;
  margin-bottom: 20px;
}

input[type="text"],
input[type="password"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
}

button[type="submit"] {
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  cursor: pointer;
}

.error {
  color: red;
  margin-top: 10px;
}
  </style>
  