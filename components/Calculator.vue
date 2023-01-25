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
            </div>
        </div>
        <div class="resultados">
            <button class="btn-calcular" @click="calcular">Calcular</button>
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
                let gasto = (parseInt(this.dados.moradia) + parseInt(this.dados.servicos) + parseInt(this.dados.transporte) + parseInt(this.dados.alimentacao) + parseInt(this.dados.saude) + parseInt(this.dados.educacao))
                let resultado = parseInt(this.dados.rendimento) - (parseInt(this.dados.moradia) + parseInt(this.dados.servicos) + parseInt(this.dados.transporte) + parseInt(this.dados.alimentacao) + parseInt(this.dados.saude) + parseInt(this.dados.educacao))
                this.total = gasto
            }
        },
    }
</script>

<style scoped>
    .container{
        width: 100%;
    }
    input{
        border: solid 1px black;   
        border-radius: 5px;
        width: 300px;
        height: 30px;
        background-color: rgb(255, 255, 255);
        text-align: center;
    }
    .rendimento{
        margin-left: 40px;
    }
    .gastos-essenciais{
        margin-left: 40px;
    }
    .btn-calcular{
        width: 100px;
        height: 30px;
        background-color: rgb(0, 0, 161);
        color: white;
        border: solid 5px rgb(0, 0, 161);
        border-radius: 10px;
    }
    .texts{
        margin: 20px 40px;
        margin-top: 50px;
    }
    h2{
        margin: 20px 0px;
    }
    h3{
        margin: 20px 0px;
    }
    .resultados{
        margin: 30px 40px;
    }

</style>