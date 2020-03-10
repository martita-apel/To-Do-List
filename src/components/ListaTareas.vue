<template>
  <div class="cuerpo_lista">
    <h1>{{ titulo }}</h1>
    <p class="bajada">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Modi illum
      beatae a unde impedit neque eaque dolorum labore accusamus eligendi,
      adipisci optio mollitia fuga at corporis pariatur!
      <span class="resaltar">Dolore, temporibus velit!</span>
    </p>

    <br />

    <!-- Lista -->
    <div class="crear_lista">
      <label class="tarea">Ingresa una nueva tarea:</label>
      <br />
      <input class="input" type="text" v-model="tarea" />
      <button class="boton" @click="crearTarea">
        <i class="fas fa-plus"></i>AGREGAR TAREA
      </button>
    </div>
    <div class="lista" v-for="(tarea, index) in tareas" :key="index">
      <ul>
        <li><input class="check" type="checkbox" />{{ tarea }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ListaTareas",
  props: {
    titulo: String
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
    crearTarea: function() {
      this.tareas.push(this.tarea);
      this.tarea = "";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bajada {
  width: 50%;
  margin: 0 auto;
}
.resaltar {
  color: #42b983;
  font-weight: bold;
}
.crear_lista {
  display: inline;
}
.tarea {
  font-weight: bold;
  font-size: 20px;
}
.input {
  width: 200px;
  height: 20px;
  margin: 10px;
}
.boton {
  margin: 10px;
  padding: 6px 10px;
  border-radius: 5px;
  border: #42b983;
  background-color: #42b983;
  color: white;
  font-weight: bold;
}
.boton:hover {
  background-color: #6effbe;
  color: #42b983;
}
.boton i {
  padding-right: 7px;
}
.lista {
  text-align: left;
  margin-left: 34%;
  font-size: 20px;
  font-weight: lighter;
}
.lista li {
  list-style: none;
}
.check {
  margin-right: 15px;
}
</style>
