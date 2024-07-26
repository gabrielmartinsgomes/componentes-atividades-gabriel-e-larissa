<script setup>
  import ResultadoForms from './components/ResultadoForms.vue';
  import InputForms from './components/InputForms.vue';
  import { computed, ref, reactive } from 'vue';

  const infos = reactive({
    nome: '',
    senha: '',
    confirmar: '',
    nascimento: '',
    email: '',
    cidade: '',
    endereco: '',
    hobbies: [],
    bio: ''
  });


const mostrarBotao = computed(() => {
  return mostrarResultado.value ? 'Esconder' : 'Mostrar';
});
const mostrarResultado = ref(false);


</script>

<template>
  <div v-if="!mostrarResultado">
    <form @submit.prevent="mostrarResultado = !mostrarResultado">
      <InputForms :infos-form="infos"/>
   <button v-if="infos.senha ==infos.confirmar && infos.senha.length >= 3" @click="mostrarResultado = !mostrarResultado" type="submit">{{ mostrarBotao }}</button>
    </form>
    </div>
    <div v-if="mostrarResultado">
      <form>
   <ResultadoForms :info="infos" />
    <button  @click="mostrarResultado = !mostrarResultado">{{ mostrarBotao }}</button>
  </form>
    </div>
</template>