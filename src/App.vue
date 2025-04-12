<template>
  <div id="app" class="container mt-5">
    <h3 class="title is-4">Cadastro:</h3>
    <p class="has-text-danger" v-show="deuErro">Preencha todos os campos!</p>

    <div class="field">
      <div class="control">
        <input class="input" type="text" placeholder="Nome" v-model="nomeField">
      </div>
    </div>

    <div class="field">
      <div class="control">
        <input class="input" type="email" placeholder="Email" v-model="emailField">
      </div>
    </div>

    <div class="field">
      <div class="control">
        <input class="input" type="number" placeholder="Idade" v-model="idadeField">
      </div>
    </div>

    <div class="field">
      <div class="control">
        <button class="button is-primary" @click="adicionarCliente">Adicionar</button>
      </div>
    </div>

    <hr>

    <div>
      <div v-for="(cliente, index) in orderClientes" :key="cliente.id" class="box">
        <h4 class="subtitle is-5">Cliente {{ index + 1 }}</h4>
        <Cliente :cliente="cliente" @deletarClienteEvent="deletarCliente($event)" />
      </div>
    </div>
  </div>
</template>

<script>
import _ from "lodash";
import Cliente from "./components/Cliente";

export default {
  components: { Cliente },
  data() {
    return {
      nomeField: "",
      emailField: "",
      idadeField: 0,
      deuErro: false,
      cliente: [
        { id: 1, nome: "Marcio Silva", email: "marcio@email.com", idade: 52 },
        { id: 2, nome: "Lucas Silva", email: "lucas@email.com", idade: 12 },
        { id: 3, nome: "José Silva", email: "jose@email.com", idade: 42 },
        { id: 4, nome: "Ruan Silva", email: "ruan@email.com", idade: 22 },
        { id: 5, nome: "Bruno Silva", email: "bruno@email.com", idade: 32 }
      ]
    };
  },
  methods: {
    adicionarCliente() {
      if (this.nomeField === "" || this.emailField === "" || this.idadeField === 0) {
        this.deuErro = true;
        alert("Preencha todos os campos!");
      } else {
        this.cliente.push({
          nome: this.nomeField,
          email: this.emailField,
          idade: this.idadeField,
          id: Date.now()
        });
        this.nomeField = "";
        this.emailField = "";
        this.idadeField = 0;
        this.deuErro = false;
      }
    },
    deletarCliente($event) {
      const id = $event.idCliente;
      this.cliente = this.cliente.filter((cliente) => cliente.id !== id);
    }
  },
  computed: {
    orderClientes() {
      return _.orderBy(this.cliente, ["nome"], ["asc"]);
    }
  }
};
</script>
