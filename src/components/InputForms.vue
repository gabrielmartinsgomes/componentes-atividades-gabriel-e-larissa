<script setup>
defineProps({
    infosForm: {
        type: Object,
        required: true
    }
})

const Estados = [
    { sigla: 'AC', nome: 'Acre' },
    { sigla: 'AL', nome: 'Alagoas' },
    { sigla: 'AP', nome: 'Amapá' },
    { sigla: 'AM', nome: 'Amazonas' },
    { sigla: 'BA', nome: 'Bahia' },
    { sigla: 'CE', nome: 'Ceará' },
    { sigla: 'DF', nome: 'Distrito Federal' },
    { sigla: 'ES', nome: 'Espírito Santo' },
    { sigla: 'GO', nome: 'Goiás' },
    { sigla: 'MA', nome: 'Maranhão' },
    { sigla: 'MT', nome: 'Mato Grosso' },
    { sigla: 'MS', nome: 'Mato Grosso do Sul' },
    { sigla: 'MG', nome: 'Minas Gerais' },
    { sigla: 'PA', nome: 'Pará' },
    { sigla: 'PB', nome: 'Paraíba' },
    { sigla: 'PR', nome: 'Paraná' },
    { sigla: 'PE', nome: 'Pernambuco' },
    { sigla: 'PI', nome: 'Piauí' },
    { sigla: 'RJ', nome: 'Rio de Janeiro' },
    { sigla: 'RN', nome: 'Rio Grande do Norte' },
    { sigla: 'RS', nome: 'Rio Grande do Sul' },
    { sigla: 'RO', nome: 'Rondônia' },
    { sigla: 'RR', nome: 'Roraima' },
    { sigla: 'SC', nome: 'Santa Catarina' },
    { sigla: 'SP', nome: 'São Paulo' },
    { sigla: 'SE', nome: 'Sergipe' },
    { sigla: 'TO', nome: 'Tocantins' }
]
</script>
<template>
  <h1>SUAS INFORMAÇÕES</h1>
                        <div class="label">
                            <label for="name">Nome</label>
                            <input type="text" v-model.trim="infosForm.nome" placeholder="Digite seu nome" id="name"
                                required />
                        </div>
                        <div class="label">
                            <label for="email">Email</label>
                            <input id="email" type="email" v-model.trim="infosForm.email"
                                placeholder="Digite seu email" required>
                        </div>
                        <div class="label">
                            <label for="senha">Senha</label>
                            <input id="senha" type="password" v-model.trim="infosForm.senha"
                                placeholder="Digite sua senha" required>
                        </div>
                        <div class="label">
                            <label for="confirmar">Confirmar senha</label>
                            <input id="confirmar" type="password" v-model.trim="infosForm.confirmar"
                                placeholder="Confirme sua senha" required>
                        </div>
                        <div class="label">
                            <label for="endereco">Endereço</label>
                            <input id="endereco" type="password" v-model.trim="infosForm.endereco"
                                placeholder="Rua XXX" required>
                        </div>
                        <div class="label">
                            <label for="nascimento">Nascimento</label>
                            <input id="nascimento" type="date" v-model="infosForm.nascimento"
                                placeholder="Digite o dia que nasceu " required>
                        </div>
                        <div class="label">
                            <label for="cidade">Cidade</label>
                            <input id="cidade" type="text" v-model="infosForm.cidade" placeholder="Digite sua cidade"
                                required>
                        </div>
                        <div class="label">
                            <label for="estado">Estado</label>

                            <select id="estado" value="Estado" v-model="infosForm.estado" required>
                                <option v-for="Estado of Estados" :key="Estado.sigla" :value="Estado.sigla">
                                    {{ Estado.nome }}
                                </option>
                            </select>
                        </div>
                        <div>
                            <p class="titulo">Hobbies:</p>
                            <input type="checkbox" id="hobbies1" value="Esporte" v-model="infosForm.hobbies">
                            <label for="hobbies1">Esportes</label>

                            <input type="checkbox" id="hobbies2" value="Ler" v-model="infosForm.hobbies">
                            <label for="hobbies2">Ler</label>

                            <input type="checkbox" id="hobbies3" value="Música" v-model="infosForm.hobbies">
                            <label for="hobbies3">Ouvir Músicas</label>

                            <input type="checkbox" id="hobbies4" value="Videogame" v-model="infosForm.hobbies">
                            <label for="hobbies4">Jogar Videogames</label>

                            <input type="checkbox" id="hobbies5" value="Assistir" v-model="infosForm.hobbies">
                            <label for="hobbies5">Assistir TV/Séries</label>

                            <input type="checkbox" id="hobbies6" value="Redes" v-model="infosForm.hobbies">
                            <label for="hobbies5">Usar redes sociais</label>

                            <input type="checkbox" id="hobbies7" value="Outros" v-model="infosForm.hobbies">
                            <label for="hobbies5">Outros</label>
                        </div>
                        <div class="bio">
                            <label for="bio">Biografia</label>
                            <textarea type="text" id="bio" placeholder="Biografia (opcional)"
                                v-model="infosForm.bio"></textarea>
                        </div>
</template>