<template>
    <div class="auth-container">
      <h2>Login</h2>
      <form @submit.prevent="handleLogin">
        <div class="form-group">
          <label for="email">Email</label>
          <input 
            type="email" 
            id="email" 
            v-model="email" 
            required 
            placeholder="Seu email"
          >
        </div>
        <div class="form-group">
          <label for="password">Senha</label>
          <input 
            type="password" 
            id="password" 
            v-model="password" 
            required 
            placeholder="Sua senha"
          >
        </div>
        <button type="submit" class="btn">Entrar</button>
      </form>
      <p class="auth-link">
        Não tem uma conta? <router-link to="/register">Registre-se</router-link>
      </p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LoginView',
    data() {
      return {
        email: '',
        password: ''
      }
    },
    methods: {
      handleLogin() {
        // Aqui você implementaria a lógica de login
        console.log('Login com:', this.email, this.password);
        // Simulação: redirecionar após login
        this.$router.push('/dashboard');
      }
    }
  }
  </script>
  
  <style scoped>
  .auth-container {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
    margin-top: 50px;
  }
  
  h2 {
    text-align: center;
    margin-bottom: 20px;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input {
    width: 100%;
    padding: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
  }
  
  .btn {
    width: 100%;
    padding: 10px;
    background-color: #42b983;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  
  .btn:hover {
    background-color: #369f6e;
  }
  
  .auth-link {
    text-align: center;
    margin-top: 15px;
  }
  </style>