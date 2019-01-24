<template>
  <div>
    <form @submit="addTodo">
      <input
        required
        type="text"
        v-model="title"
        name="title"
        placeholder="What's on your mind?"
        autocomplete="off"
        autofocus
      >
      <input type="submit" value="Add Todo" class="btn">
    </form>
  </div>
</template>

<script>
// import uuid from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      if (this.title) {
        const newTodo = {
          // id: uuid.v4(),
          title: this.title,
          completed: false
        };
        this.$emit("add-todo", newTodo);

        this.title = "";
      }
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
  padding: 10px;
}

input[type="text"],
input[type="text"]:focus {
  flex: 10;
  padding: 5px;
  border: none;
  margin-right: 10px;
  border-bottom: 1px solid slateblue;
  outline: none;
  font-size: 1.1em;
}

input[type="submit"] {
  flex: 2;
}
</style>
