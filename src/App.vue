<template>
  <div id="app">
   <TodoHeader></TodoHeader>
   <TodoInput v-on:addTodo="addTodo"></TodoInput>
   <TodoList v-bind:propsdata="todoItems" v-on:removeTodo="removeTodo"></TodoList>
   <TodoFooter v-on:removeAll="clearAll"></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from '@/components/TodoFooter.vue'

export default {
  data(){
    return {
      todoItems: []
    }
  },
  components: {
    'TodoHeader': TodoHeader,
    'TodoInput': TodoInput,
    'TodoList': TodoList,
    'TodoFooter': TodoFooter
  },
  methods: {
    created(){
        if(localStorage.length > 0){
            for(var i=0; i<localStorage.length; i++){
                this.todoItems.push(localStorage.key(i))
            }
        }
    },
    addTodo(todoItem) {
      localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItem);
    },
    clearAll() {
      localStorage.clear();
      this.todoItems = []
    },
    removeTodo(todoItem,index) {
      localStorage.removeItem(todoItem);
      this.todoItems.splice(index,1);
    }
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
