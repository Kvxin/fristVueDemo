<template>
  <li>
    <input type="checkbox" :checked="todo.isOver" @click="Check(todo.id)" />
    <span>{{ todo.title }}</span>
    <button class="layui-btn layui-btn-warm" @click="remove(todo.id)">
      删除
    </button>
  </li>
</template>

<script>
export default {
  name: "ListItem",
  props: ["todo", "checkOver", "removeTodo"],
  methods: {
    Check(id) {
      //  取反
      this.checkOver(id);
    },
    //删除
    remove(id) {
      this.removeTodo(id);
    },
  },
};
</script>

<style scoped>
li {
  width: 100%;
  height: 51px;
  margin-top: -1px;
  border: 1px solid #e4e4e4;
  padding-left: 10px;
  line-height: 50px;
  position: relative;
  user-select: none;
  border-radius: 3px;
}
li:nth-child(1) {
  margin-top: 0;
}
li:hover {
  background-color: rgba(0, 0, 0, 0.2);
}
li input[type="checkbox"] {
  cursor: pointer;
  width: 16px;
  height: 16px;
  vertical-align: middle;
}
li span {
  margin-left: 5px;
}
li button {
  position: absolute;
  top: 50%;
  left: 93%;
  transform: translate(-50%, -50%);
  display: none;
}
li:hover button {
  display: block;
}
</style>