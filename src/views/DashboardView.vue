<template>
  <div class="dashboard">
    <nav class="sidebar">
      <div class="logo">
        <h2>Dashboard</h2>
      </div>
      <ul class="menu">
        <li><a href="#" class="active">Início</a></li>
        <li><a href="#">Perfil</a></li>
        <li><a href="#">Configurações</a></li>
        <li><a href="#" @click="logout">Sair</a></li>
      </ul>
    </nav>

    <main class="content">
      <header class="top-bar">
        <h1>Bem-vindo ao Dashboard</h1>
        <div class="user-info">
          <span>Usuário</span>
        </div>
      </header>

      <div class="dashboard-content">
        <div class="card">
          <h3>Estatísticas</h3>
          <div class="stats">
            <div class="stat-item">
              <span class="number">150</span>
              <span class="label">Usuários</span>
            </div>
            <div class="stat-item">
              <span class="number">45</span>
              <span class="label">Projetos</span>
            </div>
            <div class="stat-item">
              <span class="number">12</span>
              <span class="label">Tarefas</span>
            </div>
          </div>
        </div>

        <div class="card">
          <h3>Atividades Recentes</h3>
          <ul class="activity-list">
            <li>Novo usuário registrado</li>
            <li>Projeto atualizado</li>
            <li>Tarefa concluída</li>
          </ul>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'DashboardView',
  methods: {
    logout() {
      // Implementar lógica de logout aqui
      this.$router.push('/login')
    }
  }
}
</script>

<style scoped>
.dashboard {
  display: flex;
  min-height: 100vh;
}

.sidebar {
  width: 250px;
  background-color: #2c3e50;
  color: white;
  padding: 1rem;
}

.logo {
  padding: 1rem 0;
  text-align: center;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.menu {
  list-style: none;
  padding: 0;
  margin-top: 2rem;
}

.menu li {
  margin-bottom: 0.5rem;
}

.menu a {
  color: white;
  text-decoration: none;
  padding: 0.75rem 1rem;
  display: block;
  border-radius: 4px;
  transition: background-color 0.3s;
}

.menu a:hover, .menu a.active {
  background-color: rgba(255, 255, 255, 0.1);
}

.content {
  flex: 1;
  background-color: #f5f6fa;
  padding: 2rem;
}

.top-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
}

.user-info {
  background-color: white;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.dashboard-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.card {
  background-color: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  margin-top: 1rem;
}

.stat-item {
  text-align: center;
  padding: 1rem;
  background-color: #f8f9fa;
  border-radius: 4px;
}

.number {
  display: block;
  font-size: 1.5rem;
  font-weight: bold;
  color: #2c3e50;
}

.label {
  color: #666;
  font-size: 0.9rem;
}

.activity-list {
  list-style: none;
  padding: 0;
  margin-top: 1rem;
}

.activity-list li {
  padding: 0.75rem 0;
  border-bottom: 1px solid #eee;
}

.activity-list li:last-child {
  border-bottom: none;
}
</style> 