<template>
  <div id="input">
    <form @submit.prevent v-on:submit="submitEvent()">
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
    submitEvent () {
      this.$emit('eventAdded', this.todo);
      this.todo = '';
    }
  },
}
</script>

<style scoped>
#inputField {
  width: 500px;
  height: 25px;
}
#addButton {
  margin-left: 5px;
  width: 50px;
  height: 32px;
}
#input {
  margin-top: 40px;
}
</style>
