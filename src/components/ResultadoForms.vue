<script setup>
defineProps(['infos']);
</script>

<template>
<div>
  <form @submit.prevent="salvar">
  <button @click="showContent=!showContent">{{buttonText}}</button>
  <div v-if="showContent" class="expand-box">
    <h1>Informações:</h1>
    <p>Nome:{{ infos.nome }}</p>
    <p>email: {{ infos.email }}</p>
    <p>Senha:{{ infos.senha }}</p>
    <p>Nascimento: {{ infos.nascimento }}</p>
    <p>Endereço:{{ infos.endereco }}</p>
    <p>Cidade: {{ infos.cidade }}</p>
    <p>Estado: {{ infos.estado }}</p>
    <p>Hobbies{{ infos.hobbies.join(", ") }}</p>
    <p>Biografia: {{ infos.bio }}</p>
  </div>
</form>
  
</div>
</template>