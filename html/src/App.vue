<template>
  <div id="app">
    {{ msg }}
    <input type="text" v-model="info" />
    <button @click="handleClick()">添加</button>
    <ul>
      <todo-item v-for="(item, index) in list" :key="index">
        <template v-slot:item="itemColor">
          <span
            :style="{
              fontSize: '20px',
              color: itemColor.checked ? 'red' : 'blue'
            }"
            >{{ item }}</span
          >
        </template>
      </todo-item>
    </ul>
    <router-view></router-view>
  </div>
</template>

<script>
import TodoItem from "./components/Todoitem";
export default {
  name: "app",
  components: {
    TodoItem
  },
  data() {
    return {
      msg: "hello",
      info: null,
      list: []
    };
  },
  methods: {
    handleClick() {
      console.log(this.info);
      this.list.push(this.info);
      this.info = "";
    }
  }
};
</script>
<style lang="scss"></style>
