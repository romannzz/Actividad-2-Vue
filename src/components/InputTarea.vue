<script>
export default {
    name:'InputTarea',
    data(){
        return {
            nuevaTarea:'',
            error:'',
        };
    },
    methods:{
        agregarTarea() {
            if (this.nuevaTarea.trim() === '') {
                this.error = 'La tarea no puede estar vacia';
            }else {
                this.error= '';
                this.$emit('nuevaTarea', this.nuevaTarea);
                this.nuevaTarea = '';
            }
        },
    },
};
</script>

<template>
 <div>
    <Input
     type="text"
     v-model="nuevaTarea"
     placeholder="Apunta una nueva tarea"
     />
 <button @click="agregarTarea">Agregar</button>
 <p v-if="error" class="error">{{ error }}</p>
 </div>

</template>

<style scoped>
.error {
    color: red;
    font-size: 0.9em;
}
</style>