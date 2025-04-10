<template>
  <div id="cliente">
    <h4>Nome: {{ cliente.nome }}</h4>
    <hr>
    <p>Email: {{ cliente.email }}</p>
    <p>Idade: {{ cliente.idade }}</p>
  </div>
</template>

<script>
export default {
  props: {
    cliente: Object,
    nome: String,
    email: String,
    idade: Number
  }
}
</script>


<style scoped>
    #cliente{
        background-color: rgb(223, 233, 241);
        max-width: 600px;
        height: 250px;
        padding: 1%;
        margin-top: 2%;
    }

</style>