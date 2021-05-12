<template>
  <div>
    <h1>ToDo List</h1>
    <p>You can write your ToDos in the input field and then add them to the list by clicking the add-button.</p>
  </div>

  <div v-for="(todo, index) of this.todos" :key="todo">
    {{ todo.todo }}
    <button v-on:click="del(index)" id="delButton">Delete</button>
  </div>

  <TheInput @eventAdded="addItem" />

</template>

<script>
import TheInput from "./components/TheInput";
export default {
  name: "App",
  components: {TheInput},
  data () {
    return {
      todos: [],
      counter: 0,
    }
  },
  methods: {
    addItem(todo) {
      this.todos.push({id: this.inc(), todo: todo});
      console.log('addItem: "' + TheInput.todo + '" with id ' + this.counter);
      todo = '';
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

</style>
