<template>
  <div class="box">
    <!-- 顶上的文字和提交 -->
    <Top :todos="todos" />
    <!-- 中间的list -->
    <List :todos="todos" :checkOver="checkOver" :removeTodo="removeTodo" />
    <!-- 底部 -->
    <Footer :todos="todos" :selectOver="selectOver" :clearAllTodo="clearAllTodo"/>
  </div>
</template>

<script>
import Top from "./Top.vue";
import List from "./List.vue";
import Footer from "./Footer.vue";

export default {
  name: "TodoList",
  components: { Top, List, Footer },
  props: ["todos", "checkOver", "removeTodo","selectOver","clearAllTodo"],
};
</script>

<style scoped>
.box {
  border: 1px solid #e4e4e4;
  border-radius: 3px;
  width: 800px;
  height: 530px;
  padding: 10px 10px;
}
</style>