<template>
  <div id="app" class="container">
    <h2 class="my-4">Crea una nueva tarea</h2>
    <label class="mr-2">Tarea:</label>
    <input type="text" placeholder="Ingrese nueva tarea" v-model="newToDo" />
    <button v-on:click="createToDo()">Crear</button>
    <h3 class="my-4">Lista de Tareas</h3>
    <ul>
      <li v-for="(ToDo, $index) in existingToDo" :key="$index">
        {{ $index + 1 }}: {{ ToDo.text }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'App',
  data: () => ({
    newToDo: '',
    existingToDo: []
  }),
  methods: {
    createToDo() {
      this.existingToDo.push({ text: this.newToDo }), (this.newToDo = '')
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 400px;
}

li {
  text-align: left;
}
</style>
