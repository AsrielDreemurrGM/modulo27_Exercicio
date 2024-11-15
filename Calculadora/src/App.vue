<script setup>
import { reactive } from 'vue';

import Calculadora from './components/Calculadora.vue';

const estados = reactive({
    valor1: 0,
    valor2: 0,
})

function getPrimeiroNumero(valor) {
    estados.valor1 = valor;
}

function getSegundoNumero(valor) {
    estados.valor2 = valor;
}
</script>

<template>
    <div class="container" style="height: 100vh">
        <Calculadora :valor-segundo-campo="getSegundoNumero" :valor-primeiro-campo="getPrimeiroNumero"/>
    </div>
</template>
