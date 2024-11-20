<script setup>

export default {
  
name: 'Todolist';
    props: {
        tareas: {
        type:Array;
        required: true;
        };
    };
}
</script>

<template>
<div>
    <ul>
        <li
        v-for="tarea in tareas"
        :key="tarea.id"
        :class="{ completada: tarea.completada }"
        >
        {{ tarea.titulo }}
        <button @click="$emit('completarTarea', tarea.id)">
         {{ tarea.completada ? 'Desmarcar' : 'Completar' }}
        </button>
        <button @click="$emit('eliminarTarea', tarea.id)">Eliminar</button>

        </li> 

    </ul>

</div>
</template>

<style>
ul {
    list-style: green;
    padding: 0;
    }

li{
      display:flex;
      justify-content: space-between;
      margin-bottom:10px;  
    }

.completada {
    text-decoration: line-through;
    color:gray;
    }
</style>