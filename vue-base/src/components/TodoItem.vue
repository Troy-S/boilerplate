<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
  export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
      markComplete() {
        this.todo.completed = !this.todo.completed;
      }
    }
  };
</script>

<style>
 .todo-item {
   background: #fff;
   padding: 10px;
   border-bottom: 1px #ccc dotted;
 }

 .is-complete {
   text-decoration: line-through;
 }
 
 .del {
   background: red;
   border-radius: 50%;
   border: 1px;
   color: white;
   padding: 5px 9px;
 }
</style>
