<template>
  <ul class="list-group">
    <todo v-bind:todo="t" v-for="t in todos" v-bind:key="t.id" v-on:deleteTodo="getData"></todo>
  </ul>
</template>

<script>
import todo from "../components/todo";

export default {
  name: "todos",
  props: ["todos"],
  components:{
      todo
  },
  methods:{
    getData(id){
      this.$emit("Delete",id);
    }
  }
};
</script>