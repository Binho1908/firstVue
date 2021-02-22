<template>
    <div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">
        <h4>Nome: {{cliente.nome}}</h4>
        <p>Email: {{cliente.email}}</p>
        <p v-if="showIdade === false">Idade: {{cliente.idade}}</p>
        <p v-else>O usuário escondeu a idade!</p>
        <button @click="mudarCor($event)">Mudar cor!</button>
    </div>
</template>

<script>
export default {
     data(){
         return{
             isPremium: false
         }
     },
     props: {
         cliente: Object,
         showIdade: Boolean
     },
     methods: {
         mudarCor: function($event) {
             console.log($event),
             this.isPremium = !this.isPremium;
         }
     }
}
</script>
<style scoped>

.cliente {
    background-color: #ece5e3;
    padding: 2px;
    margin-top: 2px;

}
.cliente-premium {
    background-color: #474a51;
    margin: 5px 5px 5px 5px;
    border-radius: 15px;
    box-shadow: 1px 1px 1px yellow;
    color: #daa520;
    padding: 2px;
    margin-top: 2px;
}
p, h4{
    margin: 10px;
}

 
</style>