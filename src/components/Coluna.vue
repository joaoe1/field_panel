<script setup>
import EquipmentCard from './EquipmentCard.vue';
import { computed } from 'vue';

const props = defineProps({
  titulo: String,
  status: String,
  movimentacoes: Array
  })

const movimentacoesFiltradas = computed(() => {
  return props.movimentacoes.filter(
    movimentacao => movimentacao.status === props.status
  )})

  const corStatus = computed(() => {
    cor => cor.sta
  }
  )

</script>

<template>
  <div class="coluna">
    <div class="coluna-header"
        :class="{
            'status-pendente': status === 'PENDENTE',
            'status-agendada': status === 'AGENDADA',
            'status-concluida': status === 'CONCLUIDA',
            'status-emprestado': status === 'EMPRESTADO',
            'status-devolvido': status === 'DEVOLVIDO'
        }">

    {{ titulo }} <strong>[{{ movimentacoesFiltradas.length }}]</strong>
    </div>
    <EquipmentCard
    v-for="movimentacao in movimentacoesFiltradas"
        :key="movimentacao.item"
        :item="movimentacao.item"
        :recebedor="movimentacao.recebedor"
        :executor="movimentacao.executor"
        :ticket="movimentacao.ticket"
        :data="movimentacao.data"
    />
  </div>
</template>
<style scoped>
.coluna {
  border: 1px;
  padding: 12px;
  flex: 1;
  background-color: #020617c9;
  border-radius: 8px;
  min-height: 500px;
}

.coluna-header{
    padding: 12px;
    border-radius: 6px;
    font-weight: bold;
    color: white;
    margin-bottom: 16px;;
}
.status-pendente {
    background-color: #dc2626;
    color: white;
}

.status-agendada {
    background-color: #f59e0b;
    color: white;
}

.status-concluida {
    background-color: #16a34a;
    color: white;
}

.status-emprestado {
    background-color: #2563eb;
    color: white;
}

.status-devolvido {
    background-color: #6b7280;
    color: white;
}
</style>
<style>

</style>