<template>
  <div id="app">
    <div class="container">
      <h1>Agregar tareas</h1>
    <form v-on:submit.prevent="agregarTarea">
      <h3>Tarea: <input type="text" v-model="nombre" /></h3>
      <button type="submit">  Añade  </button>
    </form>
    </div>
    <h2>Lista</h2>

    <HelloWorld :tareas="this.tareas" @deleteItem="deleteItem"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
export default {
  name: "App",
  data() {
    return {
      nombre: "",
      tareas: [],
    };
  },
  methods: {
    agregarTarea: function () {
      this.tareas.push({
        nombre: this.nombre,
      })
      this.nombre = ""
    },
    deleteItem(index){
      this.tareas.splice(index, 1)
    }
  },
  components: {
    HelloWorld,
  },
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

input{
  width: 8rem;
  margin-right: 20px;
}

body{
  display: flex;
  justify-content: center;
}
</style>