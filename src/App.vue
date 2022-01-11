<template>
  <div class="container">
    <Header title="Hello" />
    <AddTask @add-task="addTask" />
    <Tasks @toogle-task="toogleTask" @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Tasks from "./components/Tasks";
import AddTask from "./components/AddTask";

export default {
  name: "App",
  components: {
    Header,
    Tasks,
    AddTask,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    deleteTask(idd) {
      if (confirm("Sure")) {
        this.tasks = this.tasks.filter((e) => e.id !== idd);
      }
    },
    toogleTask(id) {
      // let task = this.tasks.find((e) => e.id === id);
      // task.reminder = !task.reminder;

      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
    addTask(newTask) {
      // this.tasks.push(newTask);
      this.tasks=[...this.tasks,newTask]
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Docter Appoinment 1",
        date: "March 1st at 2:40pm",
        reminder: true,
      },
      {
        id: 2,
        text: "Docter Appoinment 2",
        date: "March 1st at 2:30pm",
        reminder: true,
      },
      {
        id: 3,
        text: "Docter Appoinment 3",
        date: "March 1st at 2:50pm",
        reminder: false,
      },
    ];
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins", sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
