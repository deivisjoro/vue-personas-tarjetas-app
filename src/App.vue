<script>

import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import TarjetaEmpleado from './components/TarjetaEmpleado.vue';

export default {
  components: {
    Header,
    Footer,
    TarjetaEmpleado
  },
  data(){
    return{
      empleados: [
        {nombre: 'Camila', telefono: "245 54 54", correo: 'camila@hotmail.com'},
        {nombre: 'Jose', telefono: "422 23 23", correo: 'jose@correo.com'},
        {nombre: 'Francisco', telefono: "278 93 54", correo: 'francisco@gmail.com'},
        {nombre: 'Monica', telefono: "255 55 55", correo: 'monica@gmail.com'},
        {nombre: 'Guillermo', telefono: "378 64 23", correo: 'guillermo@correo.com'},
        {nombre: 'Maria', telefono: "123 46 87", correo: 'maria@hotmail.com'},
      ], 
      state: true //controla el estado global de todos los elementos, estan true o false
    }
  },
  methods:{
    eliminarEmpleado(index){
      this.empleados.splice(index, 1);

      //vue tiene un metodo especial para eliminar elementos de objetos o arrays
      //this.$delete(this.empleados, index); //no me funciono
    },
    activar(){
      this.state = !this.state;
      this.emitter.emit("onActiveAll", this.state);
    }
  },
  computed: {
    labelBtn(){
        return this.state ? "Desactivar todos" : "Activar todos";
    }
  }  

}

</script>

<template>

  <Header />
  <main>
    <h1>Empleados</h1>
    <hr>
    <div>
      <button @click="activar">{{ labelBtn }}</button>
    </div>
    <div class="content">
      <TarjetaEmpleado 
        v-for="(empleado, i) in empleados" 
        :key="i+empleado.nombre" 
        :nombre="empleado.nombre" 
        :telefono="empleado.telefono" 
        :correo="empleado.correo" 
        :fnEliminarEmpleado="eliminarEmpleado" 
        :index="i" 
      />
    </div>
  </main>
  
  <Footer />
  
</template>

<style>

h1{
  text-align: center;
  padding: 10px;
}

.content{
  margin-top: 35px;
  display: flex;
  flex-wrap: wrap;
}

main{
  padding: 20px;
}

</style>
