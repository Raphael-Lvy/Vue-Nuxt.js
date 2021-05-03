<template>
    <form @submit="onSubmit">
        <div class="form-control">
            <label for="text" >Tâche:</label>
            <input placeholder=" Faire les courses..."  v-model="text"/>
        </div>
        <div class="form-control">
            <label for="date">Date et heure:</label>
            <input  placeholder=" Mardi 4 mai 20h..." v-model="date"/>
        </div>
        <div class="btnContainer">
            <Button text='Ajouter' type="submit"/>
        </div>
        
    </form>
</template>


<script>
import Button from "./Button";
export default {
  name: "Task",
  components: {
    Button,
  },
  data() {
    return {
      text: "",
      date: "",
    };
  },

  methods: {
    onSubmit(e) {
      e.preventDefault();
      if (!this.text) {
        alert("Veuillez d'abord ajouter une tâche et une date s'il vous plaît");
        return;
      }
      const newTask = {
        id: Math.floor(Math.random() * 100000),
        text: this.text,
        date: this.date,
      };

      this.text = "";
      this.date = "";

      

      this.$emit('add-task', newTask);
    },
  },
};
</script>

  
<style>
form {
  width: 90%;
  margin-bottom: 30px;
}
.form-control {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  margin: 20px 0;
}

label {
  width: 30%;
  font-size: 16px;
}
input {
  width: 50%;
  font-size: 16px;
  padding: 5px;
  border-radius: 5px;
  filter:drop-shadow(0px 0px 2px gray);
}

.btnContainer {
    height: 40px;
   
}
</style>