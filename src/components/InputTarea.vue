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
                this.error= ''
            }
        }
    }
}


</script>


<template>



</template>

<style scoped>

</style>