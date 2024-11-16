<script setup>
import { reactive } from 'vue';

import Calculadora from './components/Calculadora.vue';

const estados = reactive({
    valor1: 1,
    valor2: 1,
    operacao: '/',
    resultado: 0,
})

function getPrimeiroNumero(valor) {
    estados.valor1 = parseFloat(valor);
}

function getSegundoNumero(valor) {
    estados.valor2 = parseFloat(valor);
}

function fazerConta() {
    const { operacao, valor1, valor2 } = estados;

    switch (operacao) {
        case '*':
            return (estados.resultado = valor1 * valor2);
        case '-':
            return (estados.resultado = valor1 - valor2);
        case '/':
            return (estados.resultado = valor2 !== 0 ? valor1 / valor2 : 'Erro (divisão por zero)');
        case '+':
            return (estados.resultado = valor1 + valor2);
    }
}
</script>

<template>
    <div class="container" style="height: 100vh">
        <Calculadora :trocar-operacao="evento => estados.operacao = evento.target.value"
            :valor-segundo-campo="getSegundoNumero" :valor-primeiro-campo="getPrimeiroNumero" :fazer-conta="fazerConta"
            :resultado="estados.resultado" />
    </div>
</template>
