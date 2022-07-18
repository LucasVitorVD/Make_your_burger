<template>
    <div>
        <p>Componente de mensagem</p>
        
        <div>
            <form id="burger-form">
                <div class="input-container">
                    <label for="nome">Nome do cliente:</label>
                    <input type="text" name="nome" id="nome" v-model="nome" placeholder="Nome...">
                </div>

                <div class="input-container">
                    <label for="pao">Escolha o pão:</label>
                    <select name="pao" id="pao" v-model="pao">
                        <option value="" selected>Selecione seu pão:</option>
                        <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">{{ pao.tipo }}</option>
                    </select>
                </div>

                <div class="input-container">
                    <label for="carne">Escolha a carne do seu Burger:</label>
                    <select name="carne" id="carne" v-model="carne">
                        <option value="" selected>Selecione o tipo de carne:</option>
                        <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">{{ carne.tipo }}</option>
                    </select>
                </div>

                <div class="input-container" id="opcionais-container">
                    <label id="opcionais-title" for="opcionais">Selecione os opcionais:</label>
                    <div class="checkbox-container" v-for="opcional in opcionaisData" :key="opcional.id">
                        <input type="checkbox" name="opcionais" v-model="opcionais" :value="opcional.tipo">
                        <span>{{ opcional.tipo }}</span>
                    </div>
                </div>

                <div class="input-container">
                    <input type="submit" class="submit-btn" value="Criar meu Burger!">
                </div>
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'BurgerForm',
        data() {
            return {
                paes: null,
                carnes: null,
                opcionaisData: null,
                nome: null,
                pao: null,
                carne: null,
                opcionais: [],
                status: 'Solicitado',
                msg: null
            }
        },
        methods: {
            async getIngredientes() {
                const req = await fetch("http://localhost:3000/ingredientes")
                const data = await req.json()

                this.paes = data.paes
                this.carnes = data.carnes
                this.opcionaisData = data.opcionais
            }
        },
        mounted() {
            this.getIngredientes()
        }
    }
</script>

<style scoped>
    #burger-form {
        max-width: 400px;
        margin: 0 auto;
    }

    .input-container {
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        margin-bottom: 1.3rem;
    }

    label {
        font-weight: bold;
        margin-bottom: 1rem;
        padding: 5px 10px;
        color: #222;
        border-left: 4px solid #FCBA03;
    }

    input, select {
        padding: 5px 10px;
        width: 300px;
    }

    #nome {
        font-size: .9em;
    }

    #opcionais-container {
        flex-direction: row
    }

    #opcionais-title {
        width: 100%;
    }

    .checkbox-container {
        display: flex;
        align-items: flex-start;
        width: 50%;
        margin-bottom: 1.3rem;
    }

    .checkbox-container span, .checkbox-container input {
        width: auto;
    }

    .checkbox-container span {
        margin-left: 6px;
        font-weight: bold;
    }

    .submit-btn {
        background-color: #222;
        color: #FCBA03;
        border: 2px solid #222;
        border-radius: 5px;
        font-weight: bold;
        font-size: 1em;
        padding: 10px;
        margin: 0 auto;
        cursor: pointer;
        transition: .3s;
    }

    .submit-btn:hover {
        background-color: transparent;
        color: #222;
    }
</style>