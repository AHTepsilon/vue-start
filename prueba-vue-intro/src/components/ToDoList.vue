<script>
export default {
  data() {
    return {
      tasks: [
        {
          name: "Ir a la Icesi",
          isDone: false,
        },
        {
          name: "Hacer tareas",
          isDone: false,
        },
        {
          name: "Ir a clase",
          isDone: true,
        },
      ]
    };
  },
  methods: {
    onListItemClick(task) {
      console.log("HJello");
      task.isDone = true;
      console.log(task.isDone);
    },

    onListOver(task){
        console.log("Howdy");
    }
  },
  computed: {
    doneTasks() {
      return this.tasks.filter((item) => item.isDone);
    },
    undoneTasks() {
      return this.tasks.filter((item) => !item.isDone);
    },
  },
};
</script>

<template>
  <h2>Todas las tareas</h2>
  <ul>
    <li
      class="task"
      :class="{}"
      v-for="task in tasks"
      :key="task.name"
      @click="() => onListItemClick(task)"
      @mouseenter="() => onListOver(task)"
    >
      {{ task.name }}
      <span v-if="task.isDone">😜</span>
      <span v-else-if="task.name.includes('Icesi')">👀</span>
      <span v-else>🤢</span>
    </li>
  </ul>

  <h3>Tareas Terminadas</h3>
    <ul>
    <li
      class="task"
      :class="{}"
      v-for="task in doneTasks"
      :key="task.name"
      @click="() => onListItemClick(task)"
    >
      {{ task.name }}
    </li>
  </ul>

  <h3>Tareas sin Terminar</h3>
    <ul>
    <li
      class="task"
      :class="{}"
      v-for="task in undoneTasks"
      :key="task.name"
      @click="() => onListItemClick(task)"
    >
      {{ task.name }}
    </li>
  </ul>
</template>

<style>
</style>