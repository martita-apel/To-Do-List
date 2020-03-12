<template>
  <div id="app">
    <h1>Lista de Tareas</h1>
    <p class="bajada">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Modi illum
      beatae a unde impedit neque eaque dolorum labore accusamus eligendi,
      adipisci optio mollitia fuga at corporis pariatur!
      <span class="resaltar">Dolore, temporibus velit!</span>
    </p>

    <br />

    <!-- Input de tareas -->
    <AgregarTareas @enlaceInput="pushTarea" titulo="Ingresa una nueva tarea" />

    <!-- Visualización de Lista de tareas y eliminar tarea -->
    <ListaTareas :tareas="tareas" @enlace="borrarTarea" />
  </div>
</template>

<script>
import ListaTareas from "./components/ListaTareas.vue";
import AgregarTareas from "./components/AgregarTareas.vue";

export default {
  name: "App",
  components: {
    ListaTareas,
    AgregarTareas
  },
  data() {
    return {
      tarea: "",
      tareas: [
        "Ir al supermercado",
        "Pagar internet",
        "Ir al banco",
        "Ir a buscar exámenes"
      ]
    };
  },
  methods: {
    pushTarea: function(nuevo) {
      this.tareas.push(nuevo);
    },
    borrarTarea: function(indice) {
      this.tareas.splice(indice, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.bajada {
  width: 50%;
  margin: 0 auto;
}
.resaltar {
  color: #42b983;
  font-weight: bold;
}
</style>
