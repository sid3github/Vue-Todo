<template>
  <div class="todo-list">
    <ul v-if="todos.length">
      <li v-for="(todo, index) in todos" :key="todo">
        {{ todo }}<span @click="deleteTodo(index)">&#10008;</span>
      </li>
    </ul>
    <h3 v-else>{{ msg }}</h3>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  props: ["todos", "msg"],
  data() {
    return {
      delTodos: this.todos,
    };
  },
  methods: {
    deleteTodo(index) {
      this.delTodos.splice(index, 1);
    },
  },
};
</script>

<style scoped>
ul {
  padding: unset;
}

li {
  width: 24%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  list-style: none;
  background: #e9f2ff61;
  margin: 1rem auto;
  padding: 16px;
  border-radius: 4px;
}

li:hover {
  background: #b3cff561;
}

span {
  cursor: pointer;
  transition: 0.3s;
  font-size: 18px;
}

span:hover {
  color: red;
}

@media screen and (max-width: 688px) {
  li {
    width: unset;
  }
}
</style>