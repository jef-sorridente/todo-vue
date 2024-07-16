<script setup>
const props = defineProps(["tarefas"])
</script>

<template>
    <p class="text-center h3 my-5" v-if="!props.tarefas.length">Não existem tarefas no momento!</p>
    <ul v-else class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="e => tarefa.finalizada = e.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo"
                type="checkbox">
            <label class="ms-3" :class="{ done: tarefa.finalizada }" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>
