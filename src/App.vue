<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:add Todo="addTodo"></TodoInput>
    <TodoList v-bind:propsdata="todoItems"></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'

export default {
  components: {
    'TodoHeader' : TodoHeader,
    'TodoInput' : TodoInput,
    'TodoList' : TodoList,
    'TodoFooter' : TodoFooter
  },
  data(){
    return {
      todoItems:[]
    }
  },
  methods: {
    addTodo(todoItem) {
      //input의 addTodo이벤트와 값을 받기위해서
      localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItem);
    }
  }
}
</script>

<style>
    body{
        text-align: center;
        background-color: rgba(192, 192, 192, 0.925);
    }
    input{
        border-style: groove;
        width: 200px;
    }
    button{
        border-style: groove;
    }
    .shadow{
        box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03)
    }
</style>