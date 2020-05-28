<template>
    <div id="app" class="container pt-5">
        <h2 class="mb-4">{{titulo}}</h2>

        <label>Tarea: </label>
        <input type="text" v-model="nuevaTarea" @keyup.enter="agregarTarea">

        <button @click="agregarTarea" class="btn btn-info">Agregar tarea</button>

        <h3 class="mt-5 mt-4">{{subtitulo}}</h3>

        <ul>
            <li v-for="(tarea, index) in tareas" :key="index">{{index}}: {{tarea}}</li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            titulo: 'Crea una nueva tarea',
            subtitulo: 'Lista',
            tareas: [],
            nuevaTarea: ''
        }
    },
    // Funciones
    methods: {
        agregarTarea () {
            this.tareas.push(this.nuevaTarea);
            // Limpiar input luego de agregar tarea
            this.nuevaTarea = '';
        }   
    }
}
</script>