<template>
  <div>
    <form @submit.prevent v-on:submit="addItem()">
      <input v-model="todo" id="inputField" />
      <button type="submit" id="addButton">Add</button>
    </form>
  </div>
</template>

<script>

export default {
  name: "TheInput",

  data () {
    return {
      todo: "",
    }
  },

  methods: {
  }
}
</script>

<style scoped>

</style>
