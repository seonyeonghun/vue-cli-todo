<template>
  <div id="app">
   <TodoHeader></TodoHeader>
   <TodoInput></TodoInput>
   <TodoList></TodoList>
   <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from '@/components/TodoFooter.vue'

export default {
  components: {
    'TodoHeader': TodoHeader,
    'TodoInput': TodoInput,
    'TodoList': TodoList,
    'TodoFooter': TodoFooter
  }
}
</script>

<style>
.arti-wrap {
    max-width: 74.375rem;
    margin: 50px auto;
    display: flex;
    justify-content: space-between;
}
</style>
