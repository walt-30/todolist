<template>
  <div>
    <h1>ToDo List</h1>
    <p>You can add your ToDos in the input field. And then add them by clicking the button.</p>
  </div>

  <div v-for="(todo, index) of todos" :key="todo">
    {{ todo.todo }}
    <button v-on:click="del(index)" id="delButton">Delete</button>
  </div>

  <div class="input">
    <form @submit.prevent v-on:submit="addItem">
      <input v-model="todo" id="inputField" />
      <button type="submit" id="addButton">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data () {
    return {
      todo: "",
      todos: [],
      counter: 0,
    }
  },
  methods: {
    addItem() {
      this.todos.push({id: this.inc(), todo: this.todo});
      console.log('addItem: "' + this.todo + '" with id ' + this.counter);
      this.todo = '';
    },
    inc() {
      this.counter += 1;
      return this.counter;
    },
    del(id) {
      this.todos.splice(id, 1);
      console.log('delete item with id ' + id)
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 40px;
}
#inputField {
  width: 500px;
  height: 25px;
}
#addButton {
  margin-left: 5px;
  width: 50px;
  height: 32px;
}
.input {
  margin-top: 40px;
}
</style>
