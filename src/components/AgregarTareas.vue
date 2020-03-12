<template>
  <div class="crear_lista">
    <!-- Lista input y botón -->
    <label class="tarea">{{ titulo }}</label>
    <br />
    <input class="input" type="text" v-model="tarea" />
    <button class="boton" @click="crearTarea">
      <i class="fas fa-plus"></i>AGREGAR TAREA
    </button>
  </div>
</template>

<script>
export default {
  name: "AgregarTareas",
  props: {
    titulo: String
  },
  data() {
    return {
      tarea: ""
    };
  },
  methods: {
    crearTarea: function() {
      if (this.tarea !== "") {
        this.$emit("enlaceInput", this.tarea);
        this.tarea = "";
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
</style>
