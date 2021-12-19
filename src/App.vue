<template>
  <div id="app">
    <Title />
    <TodoList
      :todos="todos"
      :checkOver="checkOver"
      :removeTodo="removeTodo"
      :selectOver="selectOver"
      :clearAllTodo="clearAllTodo"
    />
  </div>
</template>

<script>
import Title from "./components/Title.vue";
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: { Title, TodoList },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    //勾选或者取消勾选
    checkOver(id) {
      this.todos.forEach((todo) => {
        if (todo.id == id) {
          todo.isOver = !todo.isOver;
        }
      });
    },
    removeTodo(id) {
      //因为filter不改变原数组，所以我们创建一个新的数组存放
      this.todos = this.todos.filter((todo) => {
        return todo.id !== id;
      });
    },
    //全选或者不全选
    selectOver(d) {
      this.todos.forEach((todo) => {
        todo.isOver = d;
      });
    },
    //清除所有的值
    clearAllTodo(){
      this.todos = this.todos.filter((todo)=>{
          return !todo.isOver;
      })
    }
  },
  
};
</script>

<style>
#app {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>

