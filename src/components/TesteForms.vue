<script setup>
import { computed, ref, defineProps } from 'vue';

const emit = defineEmits(['adicionar']);

const infos = defineProps({
    nome: {
        type: String},
    email: {
        type: String},
    senha: {
        type: String},
    nascimento: {
        type: String},
    endereco: {
        type: String},
    cidade: {
        type: String},
    hobbies:  {
        type: String},
    bio: {
        type: String
    }
    
  });
const showContent = ref(false);
const buttonText = computed(() =>
  showContent.value ? 'Esconder' : 'Mostrar',
);
function salvar() {
    if (infos.nome === '' || infos.senha === '') {
      alert('Os campos nome e senha são obrigatórios');
      return;
    }
    emit('adicionar', { ...infos });
  }
</script>

<template>
<div>
    <label for="nome">Nome</label>
    <input type="text" id="nome" v-model="infos.nome" />
    <label for="email">Email</label>
    <input type="text" id="email" v-model="infos.email" />
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
    <p>Hobbies{{ infos.hobbies }}</p>
    <p>Biografia: {{ infos.bio }}</p>
  </div>
</form>
  
</div>
</template>