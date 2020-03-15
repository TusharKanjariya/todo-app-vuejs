<template>
  <div class="input-group mb-3">
    <input
      type="text"
      class="form-control"
      placeholder="Add Todo"
      aria-describedby="button-addon2"
      v-model="searchKey"
    />
    <div class="input-group-append">
      <button class="btn btn-primary" type="button" @click="sendData">Add Todo</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data:function(){
      return{
          searchKey : ''
      }
  },
  methods:{
      sendData(){
          this.$emit('addTodo',this.searchKey);
          this.searchKey = '';
      }
  }
};
</script>