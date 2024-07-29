<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
// 다른 위치에 있는 컴포넌트 불러오기
import TodoFooter from './components/TodoFooter.vue';
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';
import TodoHeader from './components/TodoHeader.vue';

export default {
  components: {
    'TodoInput': TodoInput,
    'TodoList': TodoList,
    'TodoHeader': TodoHeader,
    'TodoFooter': TodoFooter
  }
}
</script>

<style>

</style>