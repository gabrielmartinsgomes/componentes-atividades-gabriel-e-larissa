<script setup>
defineProps(['info']);
</script>


<template>
<div>
    <h1>Informações:</h1>
    <p>Nome: {{ info.nome }}</p>
    <p>Email: {{ info.email }}</p>
    <p>Senha: {{ info.senha }}</p>
    <p>Nascimento: {{ info.nascimento }}</p>
    <p>Endereço: {{ info.endereco }}</p>
    <p>Cidade: {{ info.cidade }}</p>
    <p>Estado: {{ info.estado }}</p>
    <p>Hobbies: {{ info.hobbies.join(", ") }}</p>
    <p>Biografia: {{ info.bio }}</p>
  
</div>
</template>