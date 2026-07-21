<script setup>
    const props = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro', 'editaTarefaTemp'])
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
        <div class="col">
            <input
            required
            type="text"
            placeholder="Digite aqui a descrição da tarefa"
            class="form-control"

            :value="props.tarefaTemp"
            @change="props.editaTarefaTemp"
            />
        </div>
        <div class="col-md-1">
            <button class="btn btn-primary">Cadastrar</button>
        </div>
        <div class="col-md-2">
            <select @change="props.trocarFiltro" class="form-control">
                <option value="todas">Todas as tarefas</option>
                <option value="pendentes">Pendentes</option>
                <option value="finalizadas">Finalizadas</option>
            </select>
        </div>
        </div>
    </form>
</template>