<template>
  <div class="home">
    <div class="row mt-5">
      <div class="col-md-3"></div>
      <div class="col-md-6">
        <AddTodo v-on:addTodo="addTodo"></AddTodo>
        <todos v-bind:todos="todos" v-on:Delete="deleteTodo"></todos>
      </div>
      <div class="col-md-3"></div>
    </div>
  </div>
</template>

<script>
import todos from "../components/todos";
import AddTodo from "../components/AddTodo";
export default {
  name: "Home",
  components: {
    todos,
    AddTodo
  },
  data:function(){
    return{
      todos : [
        {id:1,title:"Morning Breakfast",isComplete:true},
        {id:2,title:"Go to Office",isComplete:false},
        {id:3,title:"Meeting with a Client",isComplete:false},
      ]
    }
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(val => val.id !== id);
    },
      addTodo(text){
      let data = {
        id : Date.now(),
        title:text,
        isComplete : false
      }

      this.todos = [...this.todos,data];
    }
  }
};
</script>
