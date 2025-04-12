<template>
  <div :class="['box', isPremium ? 'has-background-dark has-text-warning' : 'has-background-info-light']">
    <h4 :class="{'gold-text': isPremium}" class="title is-5">Nome: {{ cliente.nome }}</h4>
    <p>Email: {{ cliente.email }}</p>
    <p v-if="showIdade">Idade: {{ cliente.idade }}</p>
    <p v-else>O usuário escondeu a idade!</p>

    <div class="buttons mt-2">
      <button class="button is-warning" @click="mudarCor">Mudar cor!</button>
      <button class="button is-danger" @click="deletarCliente">Deletar</button>
    </div>

    <hr>
    <p class="is-italic">ID Especial: {{ idEspecial }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPremium: false
    };
  },
  props: {
    cliente: Object,
    showIdade: {
      type: Boolean,
      default: true
    }
  },
  methods: {
    mudarCor() {
      this.isPremium = !this.isPremium;
    },
    deletarCliente() {
      this.$emit("deletarClienteEvent", { component: this, idCliente: this.cliente.id });
    }
  },
  computed: {
    idEspecial() {
      return (this.cliente.email + this.cliente.nome + this.cliente.id).toUpperCase();
    }
  }
};
</script>

<style scoped>

  .gold-text {
  color: gold;
}
</style>
