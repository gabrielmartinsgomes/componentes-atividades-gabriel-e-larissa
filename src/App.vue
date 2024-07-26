<script setup>
  import ResultadoForms from './components/ResultadoForms.vue';
  import InputForms from './components/InputForms.vue';
  import { computed, ref } from 'vue';
  import { reactive } from 'vue';
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


const mostrarResultado = ref(false);
const mostrarBotao = computed(() =>
  mostrarResultado.value ? 'Esconder' : 'Mostrar',
);

</script>

<template>
  <div>
    <div v-if="!mostrarBotao">
    <form>
    <InputForms :infos-form="infos"/>
   <button v-if="infos.senha ==infos.confirmar && infos.senha.length >= 3" @click="mostrarBotao = !mostrarBotao" type="submit">{{ mostrarResultado }}</button>
    </form>
    </div>
  <div v-if="mostrarBotao">
    <ResultadoForms :infos="infos" />
    <button  @click="mostrarBotao = !mostrarBotao">{{ mostrarResultado }}</button>
  </div>
  </div>
</template>