<template>
  <div class="footer" v-show="this.todos.length">
    <div class="footer_ltem">
      <input type="checkbox" :checked="isAll" @click="checkAll"/>
      <span>已完成{{ overItem }}/{{ this.todos.length }}</span>
      <button class="layui-btn-danger layui-btn" @click="removeSuccess()">删除所选中内容</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
  props: ["todos","selectOver","clearAllTodo"],
  data() {
    return {};
  },
  methods: {
    removeSuccess(){
       this.clearAllTodo()
    },
    checkAll(e){
      this.selectOver(e.target.checked)
    }
  },
  computed: {
    overItem() {
      return this.todos.reduce((pre,todos)=>pre+(todos.isOver?1:0),0)
    },
    isAll(){
      return this.todos.length === this.overItem && this.todos.length>0
    }
  },
};
</script>

<style scoped>
.footer {
  margin-top: 15px;
  width: 100%;
  padding-left: 65px;
  height: 50px;
  line-height: 50px;
  user-select: none;
}
.footer .footer_ltem {
  width: 100%;
  position: relative;
}
.footer .footer_ltem span {
  margin-left: 10px;
}
.footer .footer_ltem button {
  position: absolute;
  top: 50%;
  left: 75%;
  transform: translate(-50%, -50%);
}
</style>