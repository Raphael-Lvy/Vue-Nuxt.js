<template>
    <div class="todoContainer">
        <header>
            <h2>{{title}} </h2>
        </header>
        <Addtask @add-task="addTask" />
         <Tasks v-bind:tasks='tasks'  @delete-task='deleteTask' @done-task='doneTask'/>
    </div>
</template>

<script>
import Tasks from "./Tasks";

import Addtask from "./Addtask";

export default {
  name: "Todo",
  props: ["title"],
  components: {
    Tasks,

    Addtask,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    deleteTask(id) {
      setTimeout(() => {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }, 250);
    },
    doneTask(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, done: !task.done } : task
      );
    },
    addTask(newTask) {
        
        this.tasks = [...this.tasks, newTask];
    }
  },

  created() {
    this.tasks = [
      {
        id: 1,
        text: "Petit déj",
        date: "Lundi 3 mai 8h",
        done: true,
      },
      {
        id: 2,
        text: "Sport",
        date: "Lundi 3 mai 13h30",
        done: false,
      },
      {
        id: 3,
        text: "Mine Of War",
        date: "Lundi 3 mai 18h30",
        done: false,
      },
      {
        id: 4,
        text: "Drinks",
        date: "Lundi 3 mai 21h",
        done: false,
      },
    ];
  },
};
</script>

<style scoped>
.todoContainer {
  margin-top: 30px;
  width: 500px;
  padding-bottom: 50px;
  background: rgb(250, 249, 249);
  border-radius: 5px;
  filter: drop-shadow(0px 0px 3px gray);
  display: flex;
  flex-direction: column;
  align-items: center;
}
header {
  display: flex;
  justify-content: center;
   margin-bottom: -30px;
   filter:drop-shadow(1px 1px 2px gray);
   letter-spacing: 4px;
}
</style>

