<template>
    <div :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>{{ task.text }}
            <div>
                <i @click="$emit('toggle-reminder')" class="fas fa-clock" :class="[task.reminder ? 'reminder-on' : 'reminder-off']" ></i>
                <i @click="$emit('delete-task')" class="fas fa-times"></i>
            </div>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object
    }
}
</script>

<style scoped>
    .fa-times {
        color: red;
        border: solid 2px #00000000;
        padding: 3px;
        margin: 5px;
    }

    .fa-times:hover {
        color: rgb(177, 0, 0);
    }

    .task {
        background: #f4f4f4;
        margin: 5px;
        padding: 10px 20px;
        cursor: pointer;
    }

    .task.reminder {
        border-left: 5px solid green;
    }

    .reminder-on {
        color: green;
    }

    .reminder-off {
        color: gray;
    }

    .reminder-off:hover {
        color: green;
    }

    .reminder-on:hover {
        color: darkgreen;
    }

    .task h3 {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
</style>