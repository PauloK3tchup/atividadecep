<script>
import axios from "axios";
export default {
  data() {
    return {
      cep: "",
      endereco: {},
    };
  },
  methods: {
    async buscar() {
      const url = `https://viacep.com.br/ws/${this.cep}/json/`;
      const res = await axios.get(url);
      this.endereco = res.data;
    },
  },
};
</script>
<template>
  <main>
    <div class="container">
      <div class="formulario">
        <form @submit.prevent="buscar">
          <h1>Bota:</h1>
          <input v-model="cep" type="number" placeholder="1234567890" />
          <button type="submit">Botei</button>
        </form>
      </div>
      <form class="end">
        <label for="rua">Rua:</label>
        <input type="text" v-model="endereco.logradouro" /> <br />
        <label for="rua">Complemento:</label>
        <input type="text" v-model="endereco.complemento" /> <br />
        <label for="rua">Bairro:</label>
        <input type="text" v-model="endereco.bairro" /> <br />
        <label for="rua">Cidade:</label>
        <input type="text" v-model="endereco.localidade" /> <br />
        <label for="rua">Estado:</label>
        <input type="text" v-model="endereco.uf" /> <br />
        <label for="rua">IBGE:</label>
        <input type="text" v-model="endereco.ibge" /> <br />
        <label for="rua">GIA:</label>
        <input type="text" v-model="endereco.gia" /> <br />
        <label for="rua">DDD:</label>
        <input type="text" v-model="endereco.ddd" /> <br />
        <label for="rua">SIAFI:</label>
        <input type="text" v-model="endereco.siafi" /> <br />
      </form>
    </div>
  </main>
</template>
<style scoped>
div.container {
  background-color: aquamarine;
  padding: 15px;
  border-radius: 10px;
  width: fit-content;
  margin: auto;
  box-shadow: rgb(85, 91, 255) 0px 0px 0px 3px, rgb(31, 193, 27) 0px 0px 0px 6px,
    rgb(255, 217, 19) 0px 0px 0px 9px, rgb(255, 156, 85) 0px 0px 0px 12px,
    rgb(255, 85, 85) 0px 0px 0px 15px;
}

div.formulario input {
  border-radius: 10px;
  height: 20px;
  font-size: 18px;
  padding: 10px;
  border: solid 1px black;

  transition: 0.1s;
}

div.formulario input:hover {
  background-color: lightgoldenrodyellow;
}

form.end input {
  margin: 10px;
  border-radius: 10px;
  height: 20px;
  font-size: 18px;
  padding: 10px;
  border: solid 1px black;
  cursor: default;

  transition: 0.1s;
}

form.end input:hover {
  background-color: lightgoldenrodyellow;
  cursor: default;
}

div.formulario input:active {
  border: solid 3px black;
}

div.formulario button {
  margin: 10px;
  padding: 10px;
  height: 45px;
  font-size: 15px;
  border-radius: 10px;
  font-weight: bold;
  background-color: aqua;
  border: solid 3px black;
  transition: 0.1s;
}
div.formulario button:hover {
  transform: scale(1.2);
  background-color: cornflowerblue;
  cursor: pointer;
}

div.formulario button:active {
  transform: scale(01);
  background-color: crimson;
}
</style>
