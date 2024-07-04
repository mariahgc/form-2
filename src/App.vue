<script setup>
import { ref } from 'vue'

const informacoes = ref({
  nome: '',
  sobrenome: '',
  senha: '',
  confirmSenha: '',
  dataNasc: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: [],
  linguagens: '',
  bio: ''
})

let estados = [
  { name: 'AC' },
  { name: 'AL' },
  { name: 'AP' },
  { name: 'AM' },
  { name: 'BA' },
  { name: 'CE' },
  { name: 'DF' },
  { name: 'PE' },
  { name: 'PI' },
  { name: 'RJ' },
  { name: 'RN' },
  { name: 'RS' },
  { name: 'RO' },
  { name: 'RR' },
  { name: 'SC' },
  { name: 'SP' },
  { name: 'SE' },
  { name: 'TO' },
  { name: 'ES' },
  { name: 'GO' },
  { name: 'MA' },
  { name: 'MT' },
  { name: 'MS' },
  { name: 'MG' },
  { name: 'PA' },
  { name: 'PB' },
  { name: 'PR' }
]

const enviar = ref(true)
</script>

<template>
  <main>
    <form v-if="enviar">
      <h1>perfil</h1>
      <div class="row mb-4">
        <div class="col">
          <div data-mdb-input-init class="form-outline">
            <input type="text" class="form-control" v-model="informacoes.nome" placeholder="Nome" />
          </div>
        </div>

        <div class="col">
          <div data-mdb-input-init class="form-outline">
            <input
              type="text"
              class="form-control"
              v-model="informacoes.sobrenome"
              placeholder="Sobrenome"
            />
          </div>
        </div>
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input type="email" class="form-control" v-model="informacoes.email" placeholder="E-mail" />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input
          type="password"
          class="form-control"
          v-model="informacoes.senha"
          placeholder="Senha"
        />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input
          type="password"
          class="form-control"
          v-model="informacoes.confirmSenha"
          placeholder="Confirme sua senha"
        />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <label for="dataNasc">Data de nascimento:</label>
        <input
          type="date"
          id="dataNasc"
          class="form-control"
          v-model="informacoes.dataNasc"
          placeholder="Data de nascimento"
        />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input
          type="text"
          class="form-control"
          v-model="informacoes.endereco"
          placeholder="Endereço"
        />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input type="text" class="form-control" v-model="informacoes.cidade" placeholder="Cidade" />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <label class="form-label" for="estado">Estado:</label>
        <select class="form-select" id="estado" v-model="informacoes.estado">
          <option v-for="estado of estados" :key="estado">{{ estado.name }}</option>
        </select>
      </div>

      <section class="separar">
        <p>Seus Hobbies:</p>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="checkbox"
            id="esportes"
            v-model="informacoes.hobbies"
            value="esportes"
          />
          <label class="form-check-label" for="esportes">Esportes</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="checkbox"
            id="musica"
            v-model="informacoes.hobbies"
            value="musica"
          />
          <label class="form-check-label" for="musica">Música</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="checkbox"
            id="leitura"
            v-model="informacoes.hobbies"
            value="leitura"
          />
          <label class="form-check-label" for="leitura">Leitura</label>
        </div>
      </section>

      <section class="separar">
        <p>Linguagem preferida:</p>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            id="js"
            value="js"
            v-model="informacoes.linguagens"
          />
          <label class="form-check-label" for="js">JavaScript</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            id="swift"
            value="swift"
            v-model="informacoes.linguagens"
          />
          <label class="form-check-label" for="pyton">Swift</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            id="php"
            value="php"
            v-model="informacoes.linguagens"
          />
          <label class="form-check-label" for="php">PHP</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            id="c"
            value="c"
            v-model="informacoes.linguagens"
          />
          <label class="form-check-label" for="c">C</label>
        </div>
      </section>

      <div data-mdb-input-init class="form-outline mb-4">
        <textarea
          class="form-control"
          id="form6Example7"
          rows="4"
          placeholder="Biografia"
          v-model="informacoes.bio"
        ></textarea>
      </div>

      <button
        @click="enviar = false"
        data-mdb-ripple-init
        type="button"
        class="btn btn-primary btn-block mb-4"
      >
        Enviar
      </button>
    </form>
    <section v-else>
      <div>
        <h2>informacoes :</h2>
        <p>Nome: {{ informacoes.nome }}</p>
        <p>Sobrenome: {{ informacoes.sobrenome }}</p>
        <p>E-mail: {{ informacoes.email }}</p>
        <p>Senha: {{ informacoes.senha }}</p>
        <p>Endereço: {{ informacoes.endereco }}</p>
        <p>Cidade: {{ informacoes.cidade }}</p>
        <p>Estados: {{ informacoes.estado }}</p>
        <p>Hobbies: {{ informacoes.hobbies }}</p>
        <p>Linguagem favorita: {{ informacoes.linguagens }}</p>
        <p>Biografia: {{ informacoes.bio }}</p>
      </div>

      <button
        @click="enviar = true"
        data-mdb-ripple-init
        type="button"
        class="btn btn-primary btn-block mb-4"
      >
        Voltar
      </button>
    </section>
  </main>
</template>

<style scoped>
main {
  margin-left: 50%;
  width: 70%;
}

.separar {
  margin-top: 5%;
  margin-bottom: 5%;
}

form {
  margin-top: 10%;
}
</style>

