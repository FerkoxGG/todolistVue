<!-- Este proyecto consiste en un gestor de listas, donde ingresamos nuestras tareas por hacer en un formulario y se muestran seguidamente en una lista después de hacer clic sobre el botón de crear -->

<template>
  <div id="app">
    <h1>Crea una nueva tarea</h1>
    <form>
      <label for="task">Tarea</label>
      <input type="text" id="task" v-model="task" />
      <button type="button" @click="addTask">Crear</button>
    </form>
    <h1>Lista</h1>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        {{ task.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      task: "",
      tasks: []
    };
  },
  methods: {
    addTask() {
      this.tasks.push({
        name: this.task,
      });
      this.task = "";
    },
  },
};
</script>

<style>
#app {
  font-family: "Arial";
  font-size: 30px;
  text-align: center;
}
</style>
