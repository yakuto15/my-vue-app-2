<template>
  <div class="todolist">
    <div class="title">Todoリスト</div>
    <div>
      <div v-for="(todo, index) in todos" v-bind:key="index" class="todo">
        <div class="todo__checkbox">
          <div v-if="todo.isDone === false" class="todo__text">
            <input type="checkbox" v-model="todo.isDone" />
            <div class="box-text">{{ index }}:{{ todo.text }}</div>
            <div v-on:click="deleteTodo(index)" class="todo__delete">削除</div>
          </div>
        </div>
      </div>
    </div>
    <div>
      <div class="submit">
        <input type="text" maxlength="20" v-model="inputTodo" />
        <div v-on:click="addTodo" class="addButton">追加</div>
      </div>
    </div>
    <div class="finish-box">
      <div class="finish-list">完了リスト</div>
      <div v-for="(todo, index) in todos" v-bind:key="index" class="todo">
        <div v-if="todo.isDone" class="todo__text todo__text--done">
          {{ index }}:{{ todo.text }}
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      inputTodo: "",
      todos: [
        {
          text: "ひき肉を300g買う",
          isDone: false,
        },
        {
          text: "ホウレンソウを1束買う",
          isDone: false,
        },
        {
          text: "ピーマンを2個買う",
          isDone: false,
        },
      ],
    }
  },
  methods: {
    addTodo() {
      if (this.inputTodo !== "") {
        const todo = { text: this.inputTodo, isDone: false }
        this.todos.push(todo)
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1)
    },
  },
}
</script>

<style scoped>
.todolist {
  padding-left: 5rem;
  padding-right: 5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 50px;
  margin-top: 100px;
}

.todo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem;
  border-radius: 5px;
}

.todo__checkbox {
  display: flex;
}
.todo:hover {
  color: white;
  background-color: #b23b61;
}

.todo__text {
  text-align: center;
  display: flex;
  width: 100%;
}
.box-text {
  padding: 20px;
}
.todo__delete {
  margin-left: 5px;
  padding: 0.5rem 0.5rem;
  text-align: center;
  margin-top: 13px;
}

.todo__delete:hover {
  margin-left: 2rem;
  background-color: #b2ae3b;
  border-radius: 5px;
}

.finish-box {
  margin-top: 60px;
}

.submit {
  display: flex;
  margin-top: 70px;
  margin-bottom: 50px;
  font-size: 40px;
}

.addButton {
  margin-left: 45px;
}

input[type="checkbox"] {
  transform: scale(2);
  margin-top: 50px;
  margin-right: 10px;
}

input[type="text"] {
  font-size: 100%;
  width: 800px;
}
.title {
  font-size: 60px;
  color: firebrick;
  font-weight: 700;
}

.finish-list {
  margin-bottom: 30px;
}
</style>
