<template>
  <div>
    <!-- creando input con variable en el estado tarea-->
    <input class="input" v-model="tarea" type="text" placeholder="Ingresa nueva tarea">
    <!-- Boton para que agregue tarea el cual tiene un evento click que ejecute método agregar -->
    <button class="boton" @click="add" >Agregar tarea </button>
    <tarea v-for="(tarea, i) in tareas" :tarea="tarea" :indice="i" :key="i" @eliminar="eliminarTarea"></tarea>
  </div>
</template>

<script>
import Tarea from './components/Tarea'
export default {
  name: "lista",
  //agregando el input en el estado
  data() {
    return {
      tarea: "",
      //arreglo vacio
      tareas: []
    }
  },
  components: {
    Tarea,
  },
  methods: {
    //creando método agregar, que enviará push a arreglo que será tareas
    add(){
      this.tareas.push(this.tarea)
      this.tarea = ""

    },
    eliminarTarea(indice){
      this.tareas.splice(indice, 1)
    }
  },

}
</script>

<style lang="scss">
  .boton {
    color: white;
    background-color: #9729B2;
    margin-left: 60px;
    padding: 10px;
    
  }
  .input {
    padding: 10px;
  }
  
</style>>
