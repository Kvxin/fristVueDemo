<template>
  <div class="top">
    <div class="layui-input-block">
      <input
        type="text"
        name="title"
        placeholder="输入要添加的事项"
        class="layui-input"
        @keyup.enter="add"
        v-model.trim="title"
      />
      <button type="button" class="layui-btn layui-btn-normal" @click="add">
        提交
      </button>
    </div>
  </div>
</template>

<script>
import { nanoid } from "nanoid";
export default {
  name: "Top",
  data() {
    return {
      title: "",
    };
  },
  props: ["todos"],
  methods: {
    add() {
      if (this.title == "") {
        window.layer.msg('未输入任何内容!'); 
      } else {
        const todoObj = { id: nanoid(), title: `${this.title}`, isOver: false };
        this.todos.unshift(todoObj);
        this.title = "";
      }
    },
  },
};
</script>

<style>
.top {
  width: 100%;
  display: flex;
  justify-content: center;
}
.top .layui-input-block {
  margin-left: 0;
  width: 650px;
}
.top .layui-input-block input {
  display: inline-block;
  width: 560px;
}
.top .layui-input-block button {
  margin-left: 10px;
  display: inline-block;
}
</style>