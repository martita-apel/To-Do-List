<template>
  <div class="cuerpo_lista">
    <!-- ciclo para recorrer la lista de tareas -->
    <div v-for="(tarea, index) in tareas" :key="index">
      <p class="lista">
        <input
          class="check"
          type="checkbox"
          @click="eliminarTarea"
          :value="index"
        />
        {{ tarea }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ListaTareas",
  props: {
    titulo: String,
    tareas: Array,
    tarea: String
  },
  methods: {
    eliminarTarea: function(event) {
      let valorBorrado = event.target.value;
      console.log(valorBorrado);
      event.target.checked = false;
      this.$emit("enlace", valorBorrado);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.lista {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: left;
  font-size: 20px;
  font-weight: lighter;
}

.check {
  margin-right: 15px;
}
</style>
