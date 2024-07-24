<script setup>
  import { reactive } from 'vue';
  const emit = defineEmits(['adicionar']);
  const infos = reactive({
    nome: '',
    email: '',
    senha: '',
    nascimento: '',
    endereco: '',
    cidade: '',
    hobbies: '',
    bio: ''
  });
  function salvar() {
    if (infos.nome === '' || infos.senha === '') {
      alert('Os campos nome e senha são obrigatórios');
      return;
    }
    emit('adicionar', { ...infos });
  }
</script>
<template>
  <form @submit.prevent="salvar">
    <div>
      <label for="nome">Nome</label>
      <input type="text" id="nome" v-model="infos.nome" />
    </div>
    <div>
      <label for="senha">Senha</label>
      <input type="text" id="senha" v-model="infos.senha" />
    </div>
    <button type="submit">Salvar</button>
  </form>
</template>