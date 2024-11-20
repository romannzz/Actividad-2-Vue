<script >

import InputTarea from './components/InputTarea.vue';
import Todolist from './components/Todolist.vue';

export default  {

name: 'App',
components : {
    Todolist,
    InputTarea,
},
data(){
    return {
            tareas: [
                {id: 1, titulo: 'Deberes de Vue', completada:false},
                {id: 2, titulo: 'Comprar la copa para los premios celo 2024-2025', completada:false},
            ],

    };
},



methods: {
    agregarTarea(tareaTitulo) {
      const nuevaTarea = {
        id: Date.now(),
        titulo: tareaTitulo,
        completada: false,
      };
      this.tareas.push(nuevaTarea);
    },
    completarTarea(id) {
      const tarea = this.tareas.find(t => t.id === id);
      if (tarea) tarea.completada = !tarea.completada;
    },
    eliminarTarea(id) {
      this.tareas = this.tareas.filter(t => t.id !== id);
    },
  },
};



</script>

<template>
<div id="app">
     <h1>Lista de tareas</h1>
     <InputTarea @nuevaTarea="agregarTarea"/>    
     <Todolist
     :tareas="tareas"
     @completarTarea="completarTarea"
     @eliminarTarea="eliminarTarea"
     />

    </div>
</template>

<style scoped>
#app {
    font-family:sans-serif;
    max-width:600px;
    margin: auto;


}

</style>
