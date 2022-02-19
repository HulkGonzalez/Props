<template>
  <div class="hello">
   <ul v-for="(tarea, index) in tareas" :key="tarea">
      <li><span>{{ index+1 }} - {{ tarea.nombre }}</span>  <button @click="deleteItem(index)">Eliminar</button></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    tareas: Array
  },
  methods:{
    deleteItem(index){
      this.$emit("deleteItem", index)
    }
  }
}
</script>

<style scoped>
  ul{
    display: flex;
    justify-content: center;
  }
  span{
    font-size: medium;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    margin-left: 1rem;
  }
  button{
    width: 5rem;
    height: 2rem;
    background: red;
    color: #fff;
    border-radius: 10%;
    margin-left: 1rem;
    border: none;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-transform: uppercase;
  }
</style>