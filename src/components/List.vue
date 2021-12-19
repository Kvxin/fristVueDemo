<template>
  <div class="list">
    <ul>
      <ListItem
        v-for="p in todos"
        :key="p.id"
        :todo="p"
        :checkOver="checkOver"
        :removeTodo="removeTodo"
      />
      <div id="NullText" v-show="todos == 0">
        当前什么也没有哦<br />快来添加一个吧~
      </div>
    </ul>
  </div>
</template>

<script>
import ListItem from "./ListItem.vue";

export default {
  name: "List",
  components: { ListItem },
  props: ["todos", "checkOver","removeTodo"],
};
</script>

<style scoped>
.list {
  width: 100%;
  height: 417px;
  margin-top: 15px;
  overflow: auto;
  position: relative;
}
.list ul {
  padding-left: 65px;
  width: 650px;
  list-style: none;
}
#NullText {
  margin-top: 40px;
  text-align: center;
  font-size: 80px;
  color: rgba(0, 0, 0, 0.1);
  user-select: none;
}
</style>