<template>
  <div :class="{'cliente': !isPremium,'cliente-premium': isPremium}">
    <h4>Nome: {{ cliente.nome }}</h4>
    <hr>
    <p>Email: {{ cliente.email }}</p>
    <p v-if="showIdade === true">Idade: {{ cliente.idade }}</p>
    <p v-else>O usuário escondeu a idade!</p>
    <button @click="mudarCor">Mudar cor!</button>
    <button @click="deletarCliente">Deletar</button> <hr>

  </div>
</template>

<script>
export default {
  data(){
    return {
      isPremium: false    
    }
  },
  props: {
    cliente: Object,
    showIdade: {
      type: Boolean
    }
  },
  methods: {
    mudarCor(){
      this.isPremium = !this.isPremium
    },
    deletarCliente(){
      this.$emit("deletarClienteEvent", {component: this, idCliente: this.cliente.id})
    }
  },
}
</script>


<style scoped>
    .cliente{
        background-color: rgb(118, 192, 252);
        max-width: 600px;
        height: 250px;
        padding: 1%;
        margin-top: 2%;
    }

    .cliente-premium{
        background-color: rgb(0, 0, 0);
        color: gold;
        max-width:600px;
        height: 250px;
        padding: 1%;
        margin-top: 2%;
    }

</style>