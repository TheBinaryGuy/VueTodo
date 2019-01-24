<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete" :checked="todo.completed">
      {{ todo.title }}
      <button class="del" @click="$emit('del-todo', todo.id)">Remove</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background-color: #f4f4f4;
  padding: 10px;
  border: 1px solid #ccc;
  margin: 10px;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background-color: #000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  cursor: pointer;
  float: right;
}
</style>
