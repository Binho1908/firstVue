<template>
  <div id="app">
    <h3>Adicione um Cadastro:</h3>
    <input type="text" placeholder="nome" v-model="nomeField"> <br>
    <input type="email" placeholder="email" v-model="emailField"> <br>
    <input type="number" placeholder="idade" v-model="idadeField"> <br>
    <button @click="cadastrarUsuario">Cadastrar</button>
    <!-- <input type="text" v-model="clienteVictor.nome">
    <input type="text" v-model="clienteVictor.email"> -->
    <div v-for="(cliente,index) in clientes" :key="cliente.id">
      <h4>{{ index +1 }}</h4>
      <Cliente :cliente="cliente"/>
    </div>
  </div>
</template>

<script>
//import Lista from './components/Lista'
import Cliente from './components/Cliente'
export default {
  name: 'App',
  data(){
    return {
        nomeField: "",
        emailField: "",
        idadeField: 0,
      clientes: [
        {
        id: 2,
        nome: "fao",
        idade: 17,
        email: "fao@gmail.com"
        },
      ]
    }
  },
  components: {
    Cliente
    //Lista
  },
  methods: {
    cadastrarUsuario: function() {
      this.clientes.push({nome: this.nomeField, email: this.emailField, idade: this.idadeField, id: Date.now()})
      this.nomeField = "";
      this.emailField = "";
      this.idadeField = "";
    }
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }
  div {
    background-color: rgba(0,0,0,0.2);
  }
  h3, div {
    text-align: center;
  }
  h3 {
    padding-top: 10px;
  }
  button {
    margin-top: 10px;
    margin-bottom: 30px;
  }
  input {
    margin-top: 10px;
  }
</style>
