<template>
    <div class="auth-container">
      <h2>Registro</h2>
      <form @submit.prevent="handleRegister">
        <div class="form-group">
          <label for="name">Nome</label>
          <input 
            type="text" 
            id="name" 
            v-model="name" 
            required 
            placeholder="Seu nome"
          >
        </div>
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
        <div class="form-group">
          <label for="confirmPassword">Confirmar Senha</label>
          <input 
            type="password" 
            id="confirmPassword" 
            v-model="confirmPassword" 
            required 
            placeholder="Confirme sua senha"
          >
        </div>
        <button type="submit" class="btn">Registrar</button>
      </form>
      <p class="auth-link">
        Já tem uma conta? <router-link to="/login">Faça login</router-link>
      </p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RegisterView',
    data() {
      return {
        name: '',
        email: '',
        password: '',
        confirmPassword: ''
      }
    },
    methods: {
      handleRegister() {
        if (this.password !== this.confirmPassword) {
          alert('As senhas não coincidem!');
          return;
        }
        
        // Aqui você implementaria a lógica de registro
        console.log('Registro com:', this.name, this.email, this.password);
        // Simulação: redirecionar após registro
        this.$router.push('/dashboard');
      }
    }
  }
  </script>
  
  <style scoped>
  /* Os mesmos estilos do LoginView podem ser reutilizados */
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