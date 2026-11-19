<script setup>
defineProps({
    item: String,
    recebedor: String,
    executor: String,
    ticket: String,
    data: String
})
</script>
<template>
    <div class="card">
        <h3>{{ item }}</h3>
        <p>Recebedor: {{ recebedor }}</p>
        <p>Executor: {{ executor }}</p>
        <p>Ticket: {{ ticket }}</p>
        <p>Data: {{ data }}</p>
    </div>    
</template>

<style scoped>
.card {
  border: 1px;
  border-radius: 8px;
  margin-bottom: 12px;
  padding: 12px;
  background-color: #0f172a;
  color: white;
}

.card p{
    margin: 4px 0;
    font-size: 14px;
}

.card h3{
    font-size: 20px;
    margin-bottom: 12px;
    margin-top: 2px;
}
</style>