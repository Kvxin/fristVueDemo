<template>
  <div class="title">
    <h1>
      {{ msg }}
    </h1>
  </div>
</template>

<script>
export default {
  name: "Title",
  data() {
    return {
      msg: "TODOLIST",
    };
  },
};
</script>

<style>
.title {
  margin-bottom: 70px;
}
h1 {
  font-size: 50px;
  letter-spacing: 20px;
  user-select: none;
}
</style>