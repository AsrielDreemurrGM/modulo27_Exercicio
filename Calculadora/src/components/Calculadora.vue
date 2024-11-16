<script setup>
const props = defineProps(['valorPrimeiroCampo', 'valorSegundoCampo', 'trocarOperacao', 'fazerConta', 'resultado'])
</script>

<template>
    <div class="row d-flex justify-content-center align-items-center bg-secondary" style="height: 100%;">
        <div class="col-md-3">
            <h1>Calculadora</h1>
            <input type="number" class="form-control"
                @keyup="props.valorPrimeiroCampo($event.target.value); props.fazerConta()"
                placeholder="Digite o primeiro valor" required>
            <input type="number" class="form-control mb-3 mt-3"
                @keyup="props.valorSegundoCampo($event.target.value); props.fazerConta()"
                placeholder="Digite o segundo valor" required>
            <input :value="props.resultado" class="form-control" placeholder="O resultado aparecerá aqui"
                disabled>
        </div>
        <div class="col-md-3 text-center">
            <p class="h6">Escolha o tipo de operacão:</p>
            <select @change="props.trocarOperacao" class="rounded-1 border-black text-center">
                <option value="/">Dividir</option>
                <option value="*">Multiplicar</option>
                <option value="+">Somar</option>
                <option value="-">Subtrair</option>
            </select>
        </div>
    </div>
</template>