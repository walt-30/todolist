<template>
  <div v-for="(todo, index) of todos" :key="index">
    {{ todo.todo }}
    <button v-on:click="deleteTodo(index)" id="delButton">Delete</button>
  </div>
</template>

<script>
export default {
  name: "ListItems",
  props: [`todos`],
  emits: ['deleteTodo'],
  methods: {
    deleteTodo (index) {
      this.$emit('deleteTodo', index);
    }
  },
}
</script>

<style scoped>
</style>
