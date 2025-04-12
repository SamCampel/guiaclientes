<template>
  <div id="app">
    
    <h3>Cadastro: </h3>
    <small id="cadastroErro" v-show="deuErro">Preencha todos os campos!</small><br>
    <input type="text" placeholder="nome" v-model="nomeField"> <br>
    <input type="email" placeholder="email" v-model="emailField"> <br>
    <input type="number" placeholder="idade" v-model="idadeField"> <br>
    <button @click="adicionarCliente">Adicionar</button> <hr>
    
    <div>
     
      <div v-for="(cliente, index) in cliente" :key="cliente.id">
        <h4>{{ index +1 }}</h4>
          <Cliente :cliente="cliente" @deletarClienteEvent="deletarCliente($event)"/>
        <hr>
        

      </div>

    </div>

  </div>
</template>
 
<script>
import Cliente from "./components/Cliente";

export default {
  deuErro: false,
  components: { Cliente },
  data() {
    return {
      nomeField: "",
      emailField: "",
      idadeField: 0,
      cliente: [
        {
          id: 1,
          nome: "Marcio Silva",
          email: "marcio@email.com",
          idade: 52
        },
        {
          id: 2,
          nome: "Lucas Silva",
          email: "lucas@email.com",
          idade: 12
        },
        {
          id: 3,
          nome: "José Silva",
          email: "jose@email.com",
          idade: 42
        },
        {
          id: 4,
          nome: "Ruan Silva",
          email: "ruan@email.com",
          idade: 22
        },
        {
          id: 5,
          nome: "Bruno Silva",
          email: "bruno@email.com",
          idade: 32
        }
      ]
    };
  },
  methods: {
        adicionarCliente() {
          if (this.nomeField === "" || this.emailField === "" || this.idadeField === 0) {
            alert("Preencha todos os campos!");
            this.deuErro = true;
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
          console.log($event);
          var id = $event.idCliente;
          this.cliente = this.cliente.filter((cliente) => cliente.id != id);
        }
    }
};
</script>

<style>

 .cadastroErro{
  color: red;
  display: none;
 }

</style>