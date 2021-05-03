<template>
<div :class="[task.done ? 'done' :'', 'task']">
    <h5 :class="[task.done ? 'textDone' :'']">{{task.text}} </h5>
    <p :class="[task.done ? 'textDone' :'']">{{task.date}} </p>
    <div class='buttons'>
        <svg   @click="onDone(task.id)" aria-hidden="true" focusable="true" data-prefix="far" data-icon="check-circle"    :class="[task.done ? 'ok' :'', 'svg-inline--fa fa-check-circle fa-w-16 svg btn']"  role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M256 8C119.033 8 8 119.033 8 256s111.033 248 248 248 248-111.033 248-248S392.967 8 256 8zm0 48c110.532 0 200 89.451 200 200 0 110.532-89.451 200-200 200-110.532 0-200-89.451-200-200 0-110.532 89.451-200 200-200m140.204 130.267l-22.536-22.718c-4.667-4.705-12.265-4.736-16.97-.068L215.346 303.697l-59.792-60.277c-4.667-4.705-12.265-4.736-16.97-.069l-22.719 22.536c-4.705 4.667-4.736 12.265-.068 16.971l90.781 91.516c4.667 4.705 12.265 4.736 16.97.068l172.589-171.204c4.704-4.668 4.734-12.266.067-16.971z"></path></svg>
        <svg  @click="onDelete(task.id)" aria-hidden="true" focusable="true" data-prefix="fas" data-icon="times" class="svg-inline--fa fa-times fa-w-11 btn" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 352 512"><path fill="currentColor" d="M242.72 256l100.07-100.07c12.28-12.28 12.28-32.19 0-44.48l-22.24-22.24c-12.28-12.28-32.19-12.28-44.48 0L176 189.28 75.93 89.21c-12.28-12.28-32.19-12.28-44.48 0L9.21 111.45c-12.28 12.28-12.28 32.19 0 44.48L109.28 256 9.21 356.07c-12.28 12.28-12.28 32.19 0 44.48l22.24 22.24c12.28 12.28 32.2 12.28 44.48 0L176 322.72l100.07 100.07c12.28 12.28 32.2 12.28 44.48 0l22.24-22.24c12.28-12.28 12.28-32.19 0-44.48L242.72 256z"></path></svg>
    </div>
</div>    
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    onDelete(id) {
      this.$emit("delete-task", id);
    },
    onDone(id) {
      this.$emit("done-task", id);
    },
  },
};
</script>

<style scoped>
.task {
  width: 80%;
  height: 60px;
  margin: 10px auto;
  background: rgb(83, 83, 83);
  color: white;
  border-radius: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 25px;
  transition: 1s;
  filter: drop-shadow(0px 0px 3px gray);
}

.task:hover {
  opacity: 0.75;
}
.task.done {
  background: green;
}

.textDone {
  text-decoration: line-through;
}

.buttons {
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 80px;
}

.btn {
  cursor: pointer;
  padding: 10px;
  background: orange;
  border-radius: 5px;
  transition: 0.25s;
  margin: 0;
}

.btn:hover {
  background: rgb(175, 5, 5);
  padding: 8px;
}

.btn.ok {
  background: rgb(175, 5, 5);
}
</style>