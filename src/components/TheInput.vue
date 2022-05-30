<template>
  <div id="input">
    <form @submit.prevent v-on:submit="submitEvent()">
      <input v-model="todo" id="inputField" />
      <b-button>
          variant="primary"
          type="submit"
          id="addButton"
      >
        Add
      </b-button>
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

#input {
  margin-top: 40px;
}
</style>
