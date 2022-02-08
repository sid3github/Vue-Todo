<template>
  <div class="todo">
    <h2>{{ title }}</h2>
    <input
      type="text"
      placeholder="Enter your todo..."
      v-model="inputValue"
      @keyup.enter="addTodo"
    />
    <button @click="addTodo">Submit</button>
    <TodoList :todos="todos" :msg="msg" />
  </div>
</template>

<script>
import TodoList from "./TodoList.vue";
export default {
  name: "Todo",
  components: {
    TodoList,
  },
  data() {
    return {
      title: "Create your list!",
      inputValue: "",
      todos: [],
      msg: "No Todos Yet!",
    };
  },
  methods: {
    addTodo() {
      if (this.inputValue != "") {
        this.todos.push(this.inputValue);
        this.inputValue = "";
        console.log(this.todos);
      } else {
        alert("Please enter a todo!");
      }
    },
  },
};
</script>

<style scoped>
input {
  width: 24%;
  border: 2px solid #aaa;
  border-radius: 4px;
  margin: 2rem auto;
  outline: none;
  padding: 8px;
  box-sizing: border-box;
  transition: 0.3s;
}

input:focus {
  border-color: #42b983;
}

button {
  padding: 8px;
  margin-left: 4px;
  border: 2px solid #aaa;
  border-radius: 4px;
  cursor: pointer;
}

button:focus {
  border-color: #42b983;
}

@media screen and (max-width: 688px) {
  input {
    width: unset;
  }
}
</style>
