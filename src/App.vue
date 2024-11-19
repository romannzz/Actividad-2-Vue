<script setup>
import InputTarea from './components/InputTarea.vue';
import Todolist from './components/Todolist.vue';

export default {

name: 'App',
components : {
    Todolist,
    InputTarea,
},
data(){
    return {
            tareas: [
                {id:1, titulo: 'Deberes de Vue', completada:false},
                {id:2, 'Comprar la copa para los premios celo 2024-2025', completada:false},
            ],

    }


}

}

</script>

<template>
 <h1>Lista de tareas</h1>




</template>

<style scoped>


</style>
