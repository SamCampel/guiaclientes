<template>
  <div id="app">
    <Cliente :cliente="clienteBruno" />
    <Cliente :cliente="clienteBruno" />
    <Cliente :cliente="clienteBruno" />
  </div>
</template>
 
<script>
import Cliente from "./components/Cliente";

export default {
  components: { Cliente },
  data() {
    return {
      clienteBruno: {
        nome: "Bruno Silva",
        email: "bruno@email.com",
        idade: 32
      }
    };
  }
};
</script>

<style scoped>
</style>