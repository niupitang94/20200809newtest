<template>
  <li class="item">
    <input type="checkbox" name="" id="" v-model="checked" />
    <slot name="item" v-bind="{ checked }"></slot>
  </li>
</template>
<script>
export default {
  data() {
    return {
      checked: false
    };
  }
};
</script>
<style lang="scss" scoped>
.item {
  color: red;
}
</style>
