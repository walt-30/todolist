<template>
  <div>
    <h1>ToDo List</h1>
    <p>You can write your ToDos in the input field and then add them to the list by clicking the add-button.</p>
  </div>

  <ListItem />
  <TheInput />

</template>

<script>
import TheInput from "./components/TheInput";
import ListItem from "./components/ListItem";
export default {
  name: "App",
  components: {ListItem, TheInput},
  data () {
    return {
      counter: 0,
    }
  },
  methods: {
    addItem() {
      ListItem.todos.push({id: this.inc(), todo: ListItem.todo});
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
