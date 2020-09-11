<template>
  <div>
      <p>{{tarea}}</p>
      <!--esto tendrá un método del componente tarea-->
      <button class="boton" @click="vaciar">Eliminar tarea</button>
  </div>
</template>

<script>

export default {
name: "Tarea",
  //componente recibe props de tarea de tipo string
  props: {
    tarea: String,
    indice: Number,
  },
  methods: {
    //le enviará un evento al papá el que se llamará eliminar
    vaciar(){
    //este es un método que recibe 2 parámetros: el primero es el nombre del evento que irá al papá que en este caso será
    //eliminar y también le pasaremos como argumento indice     
    this.$emit("eliminar", this.indice)
      },
  },
};
</script>

<style></style>
