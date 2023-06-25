<template>

    <div class="card" :class="{noActivo: !state}">
        <h3>{{ nombreFormato }}</h3>
        <hr>
        <p>{{ telefono }}</p>
        <p>{{ correo }}</p>
        <BotonState @onChangeState="state = $event" />
        <!-- $event es el parametro enviado por el emisor -->

        <button @click="fnEliminarEmpleado(index)">Eliminar</button>
        <!-- tambien llamamos a funciones del padre -->
    </div>
  
</template>

<script>
import BotonState from './BotonState.vue';
export default {
    components: {
        BotonState    
    },
    props: {
        nombre: {
            type: String,
            required: true
        },
        telefono: String,
        correo: {
            type: String,
            default: "empleado@correo.com"
        },
        index: Number,
        fnEliminarEmpleado: Function
    },
    data(){
        return {
            state: true
        }
    },
    computed: {
        nombreFormato(){
            return this.nombre[0].toUpperCase()+this.nombre.substring(1).toLowerCase();
        }
    }
}
</script>

<style scoped>
    .card{
        width: 300px;
        min-height: 150px;
        padding: 5px;
        margin: 10px;
        border: solid 1px #000;
        box-shadow: #ccc 2px 2px 1px;
    }

    .noActivo{
        border: 1px solid #f00;
    }

    h3{
        padding: 10px 0;
    }
    
    p{
        margin: 5px 0;
        padding: 5px 0;
    }
</style>