<template>
  <div>
    <div class="container">
      <div class="card">
        <div id="app" class="border">
          <h1 class="title">Lista para Tudo</h1>
          <form>
            <label>
              <input
                v-model="currentTodo"
                type="text"
                placeholder="Adicionar um item"
              />
            </label>
            <button @click.prevent="addTodo">+</button>
          </form>
          <ul>
            <li
              v-for="todo in todos"
              :key="todo.text"
              @click="toggleTodo(todo)"
            >
              <div>
                <label>
                  <input type="checkbox" :checked="todo.done" />
                </label>
                <label>
                  <del v-if="todo.done">
                    {{ todo.text }}
                  </del>
                  <span v-else>
                    {{ todo.text }}
                  </span>
                </label>
                <span class="icon" alt="delete" @click="delTodo(todo)">
                  <font-awesome-icon :icon="['fas', 'trash-alt']" />
                </span>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [{ id: 1, text: "Começe a listar", done: false }],
      currentTodo: "",
    };
  },
  methods: {
    addTodo() {
      this.todos.push({
        text: this.currentTodo,
        done: false,
      });
      this.currentTodo = "";
    },
    toggleTodo(todo) {
      // eslint-disable-next-line no-param-reassign
      todo.done = !todo.done;
    },
    delTodo(todo) {
      this.todos = this.todos.filter((el) => el.text !== todo.text);
    },
  },
};
</script>

<style>
button {
  border: 2px solid #2ecc71;
  border-radius: 100%;
  padding-right: 10px;
  padding-left: 10px;
}

input {
  border: 2px solid #2ecc71;
  border-radius: 10px;
  padding-left: 15px;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.title {
  display: block;
  font-weight: 300;
  font-size: 25px;
  letter-spacing: 1px;
}

.card {
  padding-left: 15%;
  padding-right: 15%;
}

.border {
  border: 5px solid #2ecc71;
  padding: 1rem;
  border-radius: 10px;
}
</style>
