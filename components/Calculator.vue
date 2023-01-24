<template>
    <div class="container">
        <div class="texts">
            <h2>CALCULADORA 50/30/20</h2>
            <p>A regra 50/30/20 é uma forma simples de dividir seus gastos e equilibrar suas finanças apenas dividindo seu rendimento por categorias de despesas essenciais, pessoais e financeiras.</p>
            <h3>Como a regra 50-30-20 funciona?</h3>
            <p>Primeiramente, insira o seu rendimento líquido para saber como você deveria distribuir seus gastos.</p>
        </div>
        <div class="rendimento">
            <div>
                <p>Rendimento Líquido</p>
                <input type="number" v-model="dados.rendimento">
            </div>
        </div>
        <div class="texts">
            <h3>Como estão meus gastos?</h3>
            <p> Agora, insira seus gastos estimados para cada categoria de custo para saber se eles se adequam à regra 50/30/20</p>
            <h3>Custos essenciais</h3>
            <p>Custos Essenciais são aqueles gastos as quais você não pode evitar.</p>
        </div>
        <div class="gastos-essenciais">
            <div>
                <p>Moradia</p>
                <input type="number" v-model="dados.moradia">
                <p>Serviços</p>
                <input type="number" v-model="dados.servicos">
                <p>Transporte</p>
                <input type="number" v-model="dados.transporte">
                <p>Alimentação</p>
                <input type="number" v-model="dados.alimentacao">
                <p>Saúde</p>
                <input type="number" v-model="dados.saude">
                <p>Educação</p>
                <input type="number" v-model="dados.educacao">
                <button @click="calcular">Calcular</button>
            </div>
        </div>
        <div>
            <p>Seu gasto é: <span>{{ total }}</span></p>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                dados:{
                    rendimento: 0,
                    moradia: 0,
                    servicos: 0,
                    transporte: 0,
                    alimentacao: 0,
                    saude: 0,
                    educacao: 0
                },
                total: 0,
            }
        },
        methods: {
            calcular(){
                let resultado = this.dados.moradia + this.dados.servicos + this.dados.transporte + this.dados.alimentacao + this.dados.saude + this.dados.educacao
                console.log(resultado)
            }
        },
    }
</script>

<style scoped>
    .container{
    }
    input{
        border: solid 1px black;   
        border-radius: 5px;
        width: 300px;
        height: 30px;
        background-color: rgb(238, 238, 238);
        text-align: center;
    }
    .rendimento{
        display: flex;
        justify-content: center;
    }
    .texts{
        text-align: center;
    }
    .texts h2{
        text-align: center;
        margin: 10px 0px;
    }
    .texts p{
        margin: 10px 20px;
    }
    .texts h3{
        margin: 10px 40px;
    }
    .rendimento div p{
        margin: 20px 70px;
    }
    .gastos-essenciais{
        display: flex;
        justify-content: center;
    }
    .gastos-essenciais p{
        margin: 10px 0px;
    }
</style>