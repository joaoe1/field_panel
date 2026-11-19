<script setup>
import Coluna from './components/Coluna.vue'

const movimentacoes = [
  {
    item: 'Notebook Dell',
    recebedor: 'João',
    executor: 'Emanuel',
    data: '11/11/2026',
    ticket: '90001',
    status: 'PENDENTE'
  },

  {
    item: 'Notebook Lenovo E14',
    recebedor: 'Juberto',
    executor: 'Juca',
    data: '11/11/2026',
    ticket: '93301',
    status: 'AGENDADA'
  },

  {
    item: 'Notebook Lenovo Legion',
    recebedor: 'José',
    executor: 'Marcelo',
    data: '11/11/2026',
    ticket: '90231',
    status: 'CONCLUIDA'
  }
]

const colunas = [
  {
    titulo: '🟥 Pendentes',
    status: 'PENDENTE'
  },

  {
    titulo: '🟨 Agendadas',
    status: 'AGENDADA'
  },

  {
    titulo: '🟩 Concluídas',
    status: 'CONCLUIDA'
  },

  {
    titulo: '🟦 Emprestados',
    status: 'EMPRESTADO'
  },

  {
    titulo: '⬜️ Devolvidos',
    status: 'DEVOLVIDO'
  }
]


const titulo = 'FIELD SUPPORT - TROCAS E EMPRÉSTIMOS'
</script>

<template>
  
  <div class="titulo">
    <h1>{{ titulo }}</h1>
  </div>

  <div class="colunas">
  <Coluna 
  v-for="coluna in colunas" 
  :key="coluna.status" 
  :titulo="coluna.titulo"
  :status="coluna.status"
  :movimentacoes="movimentacoes"
  />
  </div>
</template>

<style scoped>
.titulo {
    display: flex;
    justify-content: center;
    padding: 20px 0;
}

.titulo h1 {
    margin: 0;
    color: white;
}

.colunas {
  display: flex;
  gap: 20px;
  padding: 20px;
  justify-self: center;
  }
</style>