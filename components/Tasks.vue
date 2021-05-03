<template>
<div class="tasks">
    <div v-for="task in tasks" :key="task.id" >
        <Task v-bind:task='task' @delete-task="$emit('delete-task', task.id)" @done-task="$emit('done-task', task.id)"/>
    </div>
</div>    
</template>

<script>

    import Task from './Task'

    export default {
        name: 'Tasks',
        components: {
            Task
        },
        props: {
            tasks: Array
        },
        emits : ['delete-task', 'done-task']
    }
</script>

<style scoped>
    .tasks {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;

    }
</style>
  